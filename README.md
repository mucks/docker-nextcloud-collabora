# Docker nextcloud with collabora behind nginx-proxy

This compose file is running behind this nginx-proxy container
[nginx-proxy](https://github.com/JrCs/docker-letsencrypt-nginx-proxy-companion) which is connected to a network called nginx-proxy

To make the nextcloud client work behind a https nginx proxy you need to add 

```php
'overwriteprotocol' => 'https'
```

to config/config.php in the nextcloud container.
