[![Build Status](https://travis-ci.org/harvard-lil/h2o-static.png?branch=master)](https://travis-ci.org/harvard-lil/h2o-static) 


Install and Run
---------------

1. Install [Docker](https://docs.docker.com/installation/) or [Docker Toolbox](https://www.docker.com/products/docker-toolbox) and fire it up.

2. `git clone https://github.com/harvard-lil/website-static.git`

3. `cd website-static`

4. Fire up the web server and build the site: `docker-compose up`

5. Check out what you built:
   -  Docker: head to http://localhost:8080/
   -  Docker Machine/Toolbox: run `docker-machine ip` to discover the IP address of your virtualbox. Then, head to http://that-ip-address:8080/

6. Make changes to the app directory.

  Most of the time, Jekyll will notice yours changes and will automatically rebuild the site: just wait for the build to finish and refresh your browser. You'll see something like the following after a successful build:
  ```
  jekyll_1  |       Generating...
  jekyll_1  |          AutoPages: Generating tags pages
  jekyll_1  |          AutoPages: Generating categories pages
  jekyll_1  |          AutoPages: collections pages are disabled/not configured in site.config.
  jekyll_1  |         Pagination: Complete, processed 140 pagination page(s)
  jekyll_1  |                     done in 27.68 seconds.
  jekyll_1  |  Auto-regeneration: enabled for '/srv/jekyll'
  ```

  Exceptions: changes to `_config.yml`, `Gemfile`, `.htaccess`, and the contents of the `_plugins` directory will not trigger an automatic rebuild, or, even if they do, the rebuilt site might not reflect your changes.

  Errors: if the build errors out (scss syntax errors, incorrect variable names, etc.), the automatic rebuilding process may stop working.

  To manually rebuild the site/restart the automatic rebuilding process, press `control + c` and then run `docker-compose up` again.


7. When you are done, press `control + c` and then run `docker-compose down`. Then, optionally:
  - Docker: quit the Docker app
  - Docker Machine/Toolbox: run `docker-machine stop`
