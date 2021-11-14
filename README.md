## rancher-add-ssh-key-global

#### docker image will do a grep for your sshpubkey defined in docker-compose.yml, if found it will stop, if not found it will append the key to the user defined by sshuser environment variable.

```
version: '2'
services:
  getroot:
    image: public.ecr.aws/e0r8b4b0/stackgurus/alpine-addsshpubkey:latest
    environment:
      sshpubkey: ssh-rsa replace this entire variable with your key rsa-key-20210315
      sshuser: root
    stdin_open: true
    volumes:
    - /root:/hostroot/root
    tty: true
    labels:
      io.rancher.container.start_once: 'true'
      io.rancher.scheduler.global: 'true'
```
