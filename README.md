boot2docker for Dockerfiles.
==================

### docker build

 - docker build -no-cache --rm -t kzdev/centos64-base -rm=true .

### boot2docker start

 - boot2docker up

### boot2docker stop

 - boot2docker stop

### boot2docker ssh

 - boot2docker ssh

  ```
password: tcuser
```

### chef-boot2docker

 - bin/chef-docker <dockerimage_path> -r <cookbook_path>

 ```
ex. http://qiita.com/mokemokechicken/items/1a7c2058877391da2422
```

### chef-boot2docker

 - vim ~/.chef-docker-env
 - vim /bin/chef-docker

