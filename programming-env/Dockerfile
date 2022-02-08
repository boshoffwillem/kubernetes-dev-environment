FROM opensuse/tumbleweed
RUN zypper up -y
RUN zypper install -y git
RUN zypper install -y curl
RUN zypper install -y wget
RUN zypper install -y unzip
RUN zypper install -y neovim
RUN sh -c 'curl -fLo "${XDG_DATA_HOME:-$HOME/.local/share}"/nvim/site/autoload/plug.vim --create-dirs https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim'
WORKDIR /root/.config
RUN mkdir /root/code
RUN git clone https://github.com/boshoffwillem/nvim.git
RUN zypper install -y gcc
RUN zypper install -y libicu \
    && rpm --import https://packages.microsoft.com/keys/microsoft.asc \
    && wget https://packages.microsoft.com/config/opensuse/15/prod.repo \
    && mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo \
    && chown root:root /etc/zypp/repos.d/microsoft-prod.repo
RUN zypper install -y dotnet-sdk-6.0
