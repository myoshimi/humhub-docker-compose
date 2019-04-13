# humhub-docker-compose
Humhub via docker-compose

====

# Usage

There are two ways to launch docker containers. First uses "Release
version" of Humhub. Second uses Humhub development version from github
repository.

As the repository does not include the codes of Humhub itself,
you need to fetch from official web site or github repository.

## Release version

* ```git clone``` from the repository
* Download latest version of [Humhub](https://humhub.org/en/download)
  community edition
* Decompress them to ```humhub-docker-compose/humhub``` directory

``` shell
git clone https://github.com/myoshimi/humhub-docker-compose
cd humhub-docker-compose
mkdir humhub
tar xzvf <Download Directory>/humhub-1.3.12.tar.gz \
  -C <path to humhub-docker-compose>/humhub --strip=1
```

* run docker-compose-rel.yml
  * ```php/Dockerfile.rel`` is built for humhub-app container

``` shell
docker-compose -f docker-compose-rel build
docker-compose -f docker-compose-rel up -d
```

## Github version

* ```git clone``` from the repository
* Download github repository of [Humhub](https://humhub.org/en/download)

``` shell
git clone https://github.com/myoshimi/humhub-docker-compose
cd humhub-docker-compose
git clone https://github.com/humhub/humhub
docker-compose -f docker-compose-dev build
docker-compose -f docker-compose-dev up -d
```

# Non-volatile Volume

* Directory ```volumes/db``` is mounted for mariadb container
* ```humhub``` is mounted for app container

