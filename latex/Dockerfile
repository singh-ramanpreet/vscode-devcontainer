ARG VERSION

FROM ubuntu:20.04

# non interactive frontend for locales
ENV DEBIAN_FRONTEND=noninteractive \
    LANGUAGE=en_US.UTF-8 \
    LANG=en_US.UTF-8 \
    LC_ALL=en_US.UTF-8

LABEL \
    org.opencontainers.image.authors="singh.ramanpreet09@gmail.com" \
    org.opencontainers.image.documentation="https://github.com/singh-ramanpreet/vscode-devcontainers" \
    org.opencontainers.image.title="latex" \
    org.opencontainers.image.description="Latex - Visual Studio Code Remote Development Container"

# for historic releases, find mirror from https://www.tug.org/historic/
ARG TEXLIVE_MIRROR=http://mirror.ctan.org/systems/texlive/tlnet

RUN \
    # Common packages
    apt-get update \
    && apt-get install -y --no-install-recommends \
    apt-utils \
    sudo \
    ca-certificates \
    locales \
    tzdata \
    gnupg \
    wget \
    git \
    openssh-client \
    cpanminus \
    make \
    gcc \
    libc6-dev \
    # set locales
    && echo "LC_ALL=en_US.UTF-8" >> /etc/environment \
    && echo "en_US.UTF-8 UTF-8" >> /etc/locale.gen \
    && echo "LANG=en_US.UTF-8" > /etc/locale.conf \
    && locale-gen en_US.UTF-8 \
    # update certifcate
    && update-ca-certificates \
    # get texlive installer
    && mkdir /tmp/install-tl-unx \
    && wget -qO- ${TEXLIVE_MIRROR}/install-tl-unx.tar.gz | tar -xz -C /tmp/install-tl-unx --strip-components=1 \
    # texlive install settings
    && printf "%s\n" \
    "selected_scheme scheme-custom" \
    "collection-basic 1" \
    "collection-bibtexextra 1" \
    "collection-binextra 1" \
    "collection-fontsrecommended 1" \
    "collection-fontutils 1" \
    "collection-formatsextra 1" \
    "collection-langenglish 1" \
    "collection-latex 1" \
    "collection-latexextra 1" \
    "collection-latexrecommended 1" \
    "collection-luatex 1" \
    "collection-mathscience 1" \
    "collection-metapost 1" \
    "collection-pictures 1" \
    "collection-plaingeneric 1" \
    "collection-pstricks 1" \
    "collection-publishers 1" \
    "instopt_adjustpath 1" \
    "tlpdbopt_autobackup 0" \
    "tlpdbopt_install_docfiles 0" \
    "tlpdbopt_install_srcfiles 0" > /tmp/install-tl-unx/texlive.profile \
    # install
    && /tmp/install-tl-unx/install-tl \
    --repository ${TEXLIVE_MIRROR} \
    --profile=/tmp/install-tl-unx/texlive.profile \
    && tlmgr path add \
    # cleanup install dir
    && rm -rf /tmp/install-tl-unx \
    # perl packages for latexindent
    && cpanm -n -q Log::Log4perl \
    && cpanm -n -q XString \
    && cpanm -n -q Log::Dispatch::File \
    && cpanm -n -q YAML::Tiny \
    && cpanm -n -q File::HomeDir \
    && cpanm -n -q Unicode::GCString \
    # cleanup
    && apt-get remove -y \
    cpanminus \
    make \
    gcc \
    libc6-dev \
    && apt-get clean autoclean \
    && apt-get autoremove -y \
    && rm -rf /var/lib/{apt,dpkg,cache,log}/ \
    # remove doc files and man pages already installed
    && rm -rf /usr/share/man/* \
    && rm -rf /usr/share/groff/* \
    && rm -rf /usr/share/info/* \
    && rm -rf /usr/share/lintian/* \
    && rm -rf /usr/share/linda/* \
    && rm -rf /var/cache/man/* \
    && (find /usr/share/doc -depth -type f ! -name copyright -delete || true) \
    && (find /usr/share/doc -type f -name "*.pdf" -delete || true) \
    && (find /usr/share/doc -type f -name "*.gz" -delete || true) \
    && (find /usr/share/doc -type f -name "*.tex" -delete || true)

# for vscode devcontainer
# sudo user with same UID and GID as host machine
ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=1000
RUN addgroup --gid $USER_GID $USERNAME \
    && useradd $USERNAME --shell /bin/sh --create-home --uid $USER_UID --gid $USER_GID \
    && mkdir -p /etc/sudoers.d \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME \
    && rm /var/log/faillog /var/log/lastlog
