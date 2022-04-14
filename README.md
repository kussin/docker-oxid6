# Kussin | Docker OXID eShop 6

This (linux/osx) setup bootstraps an dockerized developer environment for [OXID eShop 6](https://github.com/OXID-eSales/oxideshop_ce).

## Overview

- Apache 2.4 container PHP 8.0 ([Dockerfile](container/apache/Dockerfile))
- MySQL 5.7 container ([Dockerfile](https://github.com/docker-library/mysql/blob/883703dfb30d9c197e0059a669c4bb64d55f6e0d/5.7/Dockerfile))
- MailHog container ([Dockerfile](https://github.com/mailhog/MailHog/blob/master/Dockerfile))
- phpMyAdmin container ([Dockerfile](https://hub.docker.com/r/phpmyadmin/phpmyadmin/~/dockerfile/))
- OXID eShop ([latest 6.4.x](https://github.com/OXID-eSales/oxideshop_metapackage_ce/blob/b-6.4/composer.json))
- OXID demo data

## User Guide

[User Guide](USER_GUIDE.md)

## Quickstart
1. Install [docker engine](https://docs.docker.com/engine/installation/)
2. Add `127.0.0.1 oxid6.localhost` to your etc/hosts file (if needed eg. windows)
3. Fire up container
```bash
# clone repository:
git clone https://github.com/proudcommerce/docker-oxid6.git docker_oxid6
cd docker_oxid6
# create container
docker-compose build
# fire up container
docker-compose up
```

## Configuration

### Installation
- Creating oxid project takes round about 5 minutes. It´s finished when docker log shows `OXID bootstrap completed!`).
- Shop: `http://oxid6.localhost` (or `https://oxid6.localhost` with ssl-cert-snakeoil)
- Shop admin `http://oxid6.localhost/admin/`, credentials: `admin / admin`
- MailHog: `http://oxid6.localhost:8025`
- phpMyAdmin: `http://oxid6.localhost:8080`

### Container
- If you would like to run container in background, use `docker-compose up -d` for starting container and `docker logs -f oxid6_apache` for log information (eg. composer information).

### Data
- Data (`www` and `mysql`) is storend on host: `data` directory

### Credentials
- You can change all credentials (domain, ports, database, ...) in `.env` file.

### OXID demo data
- Normally oxid demo data will be installed automatically.
- If you need a project without demo data, set `OXID_DEMODATA=false` in `.env` file.

## Support

Kussin | eCommerce und Online-Marketing GmbH<br>
Fahltskamp 3<br>
25462 Rellingen<br>
Germany

Fon: +49 (4101) 85868 - 0<br>
Email: info@kussin.de<br>

[OXID Forum: Docker Container für OXID 6](https://forum.oxid-esales.com/t/docker-container-fur-oxid-6/92282)

## License

[End-User Software License Agreement](LICENSE.md)

## Credits

- [ProudCommerce](https://www.proudcommerce.com/)

## Copyright

(c) 2006-2022 Kussin | eCommerce und Online-Marketing GmbH
