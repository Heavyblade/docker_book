FROM ruby:2.4

LABEL cristianv cristianvg2003@gmail.com

RUN apt-get update -yqq

RUN apt-get install -yqq --no-install-recommends nodejs

WORKDIR /home/rails

COPY Gemfile /home/rails/Gemfile
COPY Gemfile.lock /home/rails/Gemfile.lock

RUN bundle install

COPY . /home/rails

CMD ["rails", "s", "-b", "0.0.0.0"]
