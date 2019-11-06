# Docker nextcloud with collabora behind nginx-proxy

This compose file is running behind this nginx-proxy container
[nginx-proxy](https://github.com/JrCs/docker-letsencrypt-nginx-proxy-companion) which is connected to a network called nginx-proxy

## Instructions

* change the .env.sample to .env and fill in your information
* run docker-compose up and wait for the containers to be initialized
* open nextcloud.example.tld in a browser and fill in your admin credentials, wait for nextcloud to finish initializing
* run in another shell: docker exec -it (nextcloud app container id) /bin/ash
* install a text editor with apk add (nano/vim), edit config/config.php and add

    ```php
    'overwriteprotocol' => 'https'
    ```

* In nextcloud go into apps and download and enable the collabora app
* In nextcloud settings find the collabora menu option and set it to collabora.example.tld replacing example.tld with your domain
