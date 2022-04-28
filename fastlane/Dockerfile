FROM ruby:2.6.0-alpine

RUN apk add --update --no-cache ruby-dev build-base libxml2-dev libxslt-dev git
RUN gem install bundler:2.1.1
RUN gem i fastlane
RUN fastlane add_plugin flutter_version_manager

ENV LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8

ENTRYPOINT ["fastlane"]
CMD []
