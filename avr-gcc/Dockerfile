FROM base/archlinux
RUN pacman -Sy --noconfirm --noprogressbar base-devel svn
ADD install /
ADD PKGBUILD.5.4.0.diff /

# create user and create build dir
RUN useradd -d /tmp/build -u 1000 -g 0 build-user && \
    mkdir -p /tmp/build && \
    chown build-user /tmp/build
COPY sudoers /etc/sudoers
USER build-user

RUN /install
