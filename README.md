# update-contact
Example implementation of automatically updating contacts on new message events.


## Ready project for Running
1. Clone project
a. `git clone https://github.com/acapps/update-contact.git`
2. Navigate to directory
a. `cd update-contact`
3. Run Composer Update to download necessary components.
a. `composer update`

## Running Project with Docker

For testing I've used webdeveops' `nginx-php` container.
[WebDevOps PHP-Nginx](https://github.com/webdevops/Dockerfile/tree/develop/docker/php-nginx)

**To utilize PHP 5.6, I've used:**
[WebDevOps PHP-Nginx (PHP 5.6)](https://github.com/webdevops/Dockerfile/tree/develop/docker/php-nginx/ubuntu-15.10)

**Start up the container:**
Navigate to the `update-contact` directory

Run the following command to start the Docker Container.
`docker run -d -v $PWD:/app -p 8010:80 webdevops/php-nginx:ubuntu-15:10`

This puts the container's root in the current directory, giving it access to `vendor` and `src`.

However, we only want `src` to be the Web Root.
We therefore will modify the `Dockerfile` to:
`ENV WEB_DOCUMENT_ROOT  /app/src`