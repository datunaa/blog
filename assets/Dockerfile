FROM dshubitidze/jekyll:latest
LABEL maintainer="dshubitidze"
LABEL image="dshubitidze/blog"

# Create Type-on-strap Gemfile
RUN echo "source \"https://rubygems.org\"" >> Gemfile
RUN echo "gem 'blog', '>= 2.2.4', '< 3.0'" >> Gemfile
RUN echo "Adding the Gemfile" >> cat Gemfile

# Install the theme
RUN bundle install

# Make it accessible from outside
EXPOSE 4000

