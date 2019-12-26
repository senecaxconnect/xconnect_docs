#xConnect
xConnect Remote Management Platform is the latest enhancement to the already impressive Seneca Physical Security line of products. xConnect allows you to audit, manage, and maintain all aspects of a security installation. From camera function to storage integrity, xConnect puts you in control of your entire environment from a single, intuitive dashboard.

xConnect monitors your security environment with advanced intelligence, and empowers you to manage and maintain each and every function of your installation from a single web-based user interface. While its functionality may be expected to center around the performance monitoring of network video recorders, the application also provides command and control functionality on the device level.

This platform is designed with managed service providers in mind to enable intuitive, but powerful, enterprise level management of one or many security networks through a single pane of glass. Reduce the amount of service calls and truck rolls by getting in front of issues before your end-user realizes that something has happened.

## Audit

- Temperatures, fan speeds, power supplies
- RAID controllers, physical, logical and virtual storage
- System utilizations
- Application monitoring
- Network bandwidth analysis
- VMS Log Analysis

## Manage

- Client-less remote desktop
- Secure tunneling to private networks
- Access to Out of Band Management (iLO, iDRAC, ASMB [Seneca])
- Remote command and execution
- Designed for Service Providers managing multiple sites

## Act

- Automatic Remote Command Execution
- Mobile Push Notification
- 3rd Party API Posting
- Email notifications

### As an executable

You can invoke the container as an executable directly:

```sh
$ docker run \
  --port 3000:3000 \
  --volume /path/to/docs:/usr/local/docsify \
  littlstar/docsify
```

`docker-docsify` set the working directory to `/usr/local/docsify` in
the container. This makes it easy to bind a local path on disk to the
container. By default the container executes `docsify serve --port 3000 .`.

### From a Dockerfile

You can use the image as a base in a `Dockerfile`:

```Dockerfile
FROM littlstar/docsify
ADD /path/to/docs .
```

An image can be built and then executed.

```sh
$ docker build -t mydocs .
$ docker run -p 3000:3000 mydocs # server running on localhost:3000
```

## Building a custom docker-docsify

`docker-docsify` can be built with custom settings. This is useful for
things like enabling [ssr](https://docsify.now.sh/ssr). The `./configure`
script in this repository generates a `Dockerfile` and `Makefile`.

Clone this repository before continuing.
