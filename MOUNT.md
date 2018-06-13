## Way to setup with Docker where build server and admin.yaml is persisted across server restarts and Docker image updates.

Before Step 4 in SETUP.md, create the persistent directory on the Linux instance with

```
mkdir /srv
```

As part of Step 4 in SETUP.md, run the Docker image with
```
docker run -d --privileged -p 20-21:20-21 -p 8080-8082:8080-8082 --mount type=bind,source=/srv,target=/home/admin/srv nbake/meta /sbin/my_init
```

As part of Step 5 in SETUP.md, install the build server in the persistent directory instead of `/home/admin`

```
cd /home/admin/srv
```

As part of Step 6 in SETUP.md, configure the project paths as follows
```
cd /home/admin/srv
// edit admin.yaml. It needs a password and where to mount.
// ensure mount is set to /home/admin/prod1 and srv_www to /home/admin/srv/www_admin/
```



