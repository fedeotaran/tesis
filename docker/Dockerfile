FROM ubuntu:wily
ENV DEBIAN_FRONTEND noninteractive
MAINTAINER Federico Otaran
MAINTAINER Nicanor Perera

RUN apt-get update -q && \
    apt-get install -y gnuplot \
                       texlive-binaries \
                       texlive-lang-spanish \
                       texlive-latex-base \
                       texlive-latex-extra \
                       xindy \
                       texlive-full \
                       texlive-latex-extra \
                       python \
                       python-pip \
                       python-pygments
RUN apt-get install -y make
RUN apt-get install -y luatex \
                       texlive-luatex \
                       texlive-xetex
RUN apt-get clean
RUN rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*


WORKDIR /latex
VOLUME ["/latex"]

COPY ./entrypoint.sh /bin
RUN ["mkdir", "-p", "/usr/local/share/texmf/tex/latex/contrib"]
COPY ./support/* /usr/local/share/texmf/tex/latex/contrib/
RUN ["ln", "-s", "/usr/share/xindy/lang/spanish/modern-utf8-lang.xdy", "/usr/share/xindy/lang/spanish/utf8-lang.xdy"]
RUN ["ln", "-s", "/usr/share/xindy/lang/spanish/modern-utf8-test.xdy", "/usr/share/xindy/lang/spanish/utf8-test.xdy"]
RUN ["ln", "-s", "/usr/share/xindy/lang/spanish/modern-utf8.xdy", "/usr/share/xindy/lang/spanish/utf8.xdy"]
RUN ["texhash", "/usr/local/share/texmf"]
RUN ["mkdir", "-p", "/root/.fonts"]
COPY ./fonts /root/.fonts

ENTRYPOINT ["/bin/entrypoint.sh"]
