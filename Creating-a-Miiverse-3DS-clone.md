## Creating a Miiverse 3DS clone
This is my thank you to those who used Reverse/foxverse, big thanks to Stary who let us release the patches!

# Requirements
1. A computer with Windows or Linux.
2. Some knowledge on programming and NGINX configurations.
3. [discovery.zip](https://github.com/Cyuubi/cyuubi.github.io/raw/master/discovery.zip)
4. NGINX with PHP 7.2 FPM
5. Composer
6. Miiverse 3DS applet `code.bin`

# Before we begin
This guide assumes you have a NGINX server set up with Let's Encrypt (DST Root CA X3) and two subdomains called `discovery` and `n3ds` both with Let's Encrypt.

# Ready. Set. GO!
1. Create a directory called `discovery` in `/var/www/`.
2. Copy the contents of the files in `server` except for the `config` folder into `/var/www/discovery/`.
3. Run `composer install` in `/var/www/discovery/`, there should be no errors when running this command.
4. Copy the contents of the `config` folder into the NGINX config folder on your server, overwrite anything if asked.
5. Edit `nginx.conf`, `discovery-ssl.conf` and `n3ds-ssl.conf` to the correct path to things.
6. Edit `api-miiverse.php` in `/var/www/discovery/pages/` and replace `3DS_HOST` with `n3ds.<YOUR_DOMAIN>`.
7. Copy the `patch` folder somewhere on your computer and copy the Miiverse 3DS applet `code.bin` to the `patch` folder.
8. Edit `patch.s` folder and replace `https://3ds.denabot.pw/miiverse/xml` with `https://n3ds.<YOUR_DOMAIN>/miiverse/xml`.
9. Run `patch.bat` if your on Windows and if your on Linux run `patch.sh`, this should create a `code.ips`.
10. Copy the `code.ips` and go into `sdroot/luma/titles/` and paste `code.ips` into all 3 folders.
11. Insert your 3DS SD card and copy the contents of the `sdroot` folder into your 3DS SD card, overwrite anything if asked.
12. Enable game patching in Luma3DS and enjoy!

# What can I do with this?
You can use the cave API which the Miiverse 3DS applet has, check out [Kaeru's cave API docs](https://github.com/KaeruTeam/miiverse-docs/wiki/cave-API)!

# Support
Have any questions or issues? Join our [Discord](https://discord.gg/zpEyAhy) server!
