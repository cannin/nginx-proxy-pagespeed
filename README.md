# nginx-proxy-pagespeed

Based on combro2k/nginx-proxy

# Enable Pagespeed
To enable Pagespeed module per host
docker run .... -e PAGESPEED=1

# Run proxy
```
docker stop nginx-proxy-pagespeed; docker rm nginx-proxy-pagespeed; docker run -d --restart=always --name nginx-proxy-pagespeed -p 80:80 -v /var/run/docker.sock:/tmp/docker.sock -t cannin/nginx-proxy-pagespeed:nginx-1.11.3_pagespeed-1.11.33.2_docker-gen-0.7.1_websockets
```

# Run static website
```
docker stop tmp; docker rm tmp; docker run --restart=always --name wallpapers --expose 8080 -e VIRTUAL_HOST=tmp.example.com -e PAGESPEED=1 -v /home/ubuntu/tmp:/src -w /src -t cannin/nodejs-http-server:0.10.25
```
