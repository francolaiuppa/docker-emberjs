# docker-emberjs
frontend javascript development docker image that uses:
- node 5.3
- npm
- bower
- gulp
- ember-cli

This image is based on `francolaiuppa/docker-bower-gulp` in order to reduce
disk usage if you decide to use a single image for backend and frontend.

# How to use
You'll need to mount your application folder to `/usr/src/app` and share the ports `4200` and `49152`;

Remember to do the `npm install` and `bower install --allow-root` using the docker image
otherwise you will have to chown the files to your username.

By default the app will run `ember server` but you can easily override it:

> docker run -it --rm -p 0.0.0.0:4200:4200 -p 0.0.0.0:49152 -v $(pwd):/usr/src/app francolaiuppa/docker-nodemon-forever ember g route testing


