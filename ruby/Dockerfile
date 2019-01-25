FROM amazonlinux:2
RUN yum -y install git gcc-c++ glibc-headers openssl-devel readline libyaml-devel readline-devel zlib zlib-devel libffi-devel libxml2 libxslt libxml2-devel libxslt-devel sqlite-devel bzip2 tar make
RUN git clone https://github.com/sstephenson/rbenv.git /usr/local/rbenv
ENV RBENV_ROOT /usr/local/rbenv
ENV PATH $RBENV_ROOT/bin:$PATH
ENV eval "$(rbenv init -)"
RUN git clone https://github.com/sstephenson/ruby-build.git /usr/local/rbenv/plugins/ruby-build
RUN /usr/local/rbenv/plugins/ruby-build/install.sh
RUN rbenv install 2.5.0
RUN rbenv global 2.5.0
RUN rbenv exec gem update
RUN rbenv exec gem install bundler -v 1.17.1
CMD /bin/bash
