# PHP Wrapper

This is a very simple wrapper for deploying PHP Web-Apps onto a Dokploy server.

## How to use

1. use this repo as a template when creating your own.
    1. Alternatively, you can also just copy the files to the base-dir of your existing repo and move your app into `App/src`
2. Put your application files into the `App/src` folder
3. Connect your Git Account inside of Dokploy
4. To deploy your app, select the git provider you connected, select your repo etc. click deploy. Dokploy should handle the rest automatically.

## How it works:

Its pretty simple:  
- First, the `docker-compose.yml` file tells Dokploy what to do and how.
  - In our case, we are deploying an instance of the [frankenphp caddy server](https://frankenphp.dev/) and attaching the code of our app to it.  
- Secondly, the `Caddyfile` tells caddy what to do.
  - in this case, serve the contents of the `App/src/public` directory with php.  

## Environment Variables:

- `PHP_VERSION` -> Set this to the specific PHP Version your App needs. DEFAULT: `8.4`