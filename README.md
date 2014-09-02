docker-RVM-1.9.3
================

Docker image to run Ruby 1.9.3 applications

Usage Dockerfile example
------------------------

    FROM davidgaya/RVM-1.9.3

    # Gem dependencies
    ADD ./Gemfile /app/
    ADD ./Gemfile.lock /app/
    RUN /bin/bash -l -c "bundle"

    # NPM dependencies
    ADD ./package.json /app/
    RUN npm install

    # Add rest of source code
    ADD . /app/

    # Compile assets
    #RUN /bin/bash -l -c "bundle exec rake assets:clean"
    #RUN /bin/bash -l -c "rake assets:precompile"
    CMD /bin/bash -l -c "puma"
