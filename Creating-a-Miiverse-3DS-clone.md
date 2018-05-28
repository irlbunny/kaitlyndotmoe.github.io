## Creating a Miiverse 3DS clone
This is my thank you to those who used Reverse/foxverse, big thanks to Stary who let us release the patches!

# Requirements
1. A computer with Windows or Linux.
2. Some knowledge on programming and NGINX configurations.
3. [discovery.zip](https://github.com/Cyuubi/cyuubi.github.io/raw/master/discovery.zip)
4. NGINX with PHP 7.2 FPM
5. Composer

# Before We Begin
This guide assumes you have a NGINX server set up with Let's Encrypt (DST Root CA X3) and two subdomains called `discovery` and `n3ds` both with Let's Encrypt.

# Ready. Set. GO!
1. Create a directory called `discovery` in `/var/www/`.
2. Copy the contents of the files in `server` except for the `config` folder into `/var/www/discovery/`.
3. Run `composer install` in `/var/www/discovery/`, there should be no errors when running this command.
4. Copy the contents of the `config` folder into the NGINX config folder on your server, overwrite anything if asked.
5. Edit `nginx.conf`, `discovery-ssl.conf` and `n3ds-ssl.conf` to the correct path to things.

# Support
Have any questions or issues? Join our [Discord](https://discord.gg/zpEyAhy) server!
