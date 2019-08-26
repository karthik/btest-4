FROM rocker/binder:3.6.0
LABEL maintainer='Karthik Ram'
USER root
COPY . ${HOME}
RUN chown -R ${NB_USER} ${HOME}
USER ${NB_USER}

RUN installGithub.r thomasp85/patchwork

RUN wget https://github.com/karthik/btest-4/raw/master/DESCRIPTION && R -e "options(repos = list(CRAN = 'http://mran.revolutionanalytics.com/snapshot/2019-08-20/')); devtools::install_deps()"

RUN rm DESCRIPTION.1; exit 0
