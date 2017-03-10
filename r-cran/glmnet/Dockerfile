FROM koash/r-base:0.1.0

MAINTAINER Koichi Ashizaki

RUN apk --update add --virtual \
    build-dependencies \
    build-base \
    gcc \
    R-dev \
    make 

RUN echo "r <- getOption('repos'); r['CRAN'] <- 'http://cran.r-project.org'; options(repos = r);" > ~/.Rprofile \
 && R -e "install.packages('glmnet', dependencies = TRUE, repos = 'http://cran.r-project.org')"

RUN apk del build-dependencies

CMD ["R"]