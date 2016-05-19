#Supported tags and respective Dockerfile links

- [`0.0.1` (*0.0.1/Dockerfile*)](https://github.com/Accenture/letsencrypt/blob/master/Dockerfile)

# What is letsencrypt?

letsencrypt is a fully-featured, extensible client for the Let's
Encrypt CA (or any other CA that speaks the `ACME
<https://github.com/ietf-wg-acme/acme/blob/master/draft-ietf-acme-acme.md>`_
protocol) that can automate the tasks of obtaining certificates and
configuring webservers to use them. This client runs on Unix-based operating
systems.

# How to use this image

The easiest for to run letsencrypt image is as follow:
```
      $ docker run --rm --name=<your-container-name> -it \
        -p 80:80 -p 443:443 \
        -v <store-path>:/etc/letsencrypt
        --net=<your-network-name> \
        adop/letsencrypt:VERSION -c "command"
```
Where ```command``` is ```letsencrypt-auto``` command.

Exapmle:

```/opt/letsencrypt/letsencrypt-auto certonly --standalone -d ${DOMAIN_NAME} --text --register-unsafely-without-email --agree-tos"```

after the above letsencrypt will request ssl certs for the ```$DOMAIN_NAME``` and save to ```<store-path>```.
        
# License
Please view [licence information](LICENCE.md) for the software contained on this image.

#Supported Docker versions

This image is officially supported on Docker version 1.11.1.

# User feedback

## Documentation
Documentation for this image is available in the [letsencrypt](https://letsencrypt.org).
Additional documentaion can be found under the [`docker-library/docs` GitHub repo](https://github.com/docker-library/docs). Be sure to familiarize yourself with the [repository's `README.md` file](https://github.com/docker-library/docs/blob/master/README.md) before attempting a pull request.

## Issues
If you have any problems with or questions about this image, please contact us through a [GitHub issue](https://github.com/Accenture/letsencrypt/issues).

## Contribute
You are invited to contribute new features, fixes, or updates, large or small; we are always thrilled to receive pull requests, and do our best to process them as fast as we can.

Before you start to code, we recommend discussing your plans through a [GitHub issue](https://github.com/Accenture/letsencrypt/issues), especially for more ambitious contributions. This gives other contributors a chance to point you in the right direction, give you feedback on your design, and help you find out if someone else is working on the same thing.