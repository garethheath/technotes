version with detailed info
nginx -V

check config
nginx -t

dump config
ngnix -T

reload gracefully
ngnix -s reload

test and reload gracefully
nginx -t && nginx -s reload

logs
/var/log/nginx/access.log
/var/log/nginx/error.log

config
/etc/nginx/nginx.conf       top-level config file
/etc/nginx/conf.d/*.conf    virtual server specific config file

force connections to SSL
use http/2
