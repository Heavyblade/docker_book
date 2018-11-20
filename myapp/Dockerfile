FROM ruby:2.4

LABEL cristianv cristianvg2003@gmail.com

RUN apt-get update -yqq

RUN apt-get install -yqq --no-install-recommends apt-transport-https
RUN curl -sL https://deb.nodesource.com/setup_6.x | bash -
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list

RUN apt-get update -yqq && apt-get install -yqq --no-install-recommends nodejs yarn

WORKDIR /home/rails

COPY Gemfile* /home/rails/

RUN bundle install

COPY . /home/rails

ENTRYPOINT ["./docker-entrypoint.sh"]
CMD ["rails", "s", "-b", "0.0.0.0"]
