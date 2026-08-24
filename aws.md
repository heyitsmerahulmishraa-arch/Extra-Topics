## Check Your SSL certificate
```bash
sudo certbot certificates
```

## For Renew it
```bash
sudo certbot renew
```
if renewal fails:
```bash
sudo certbot renew --dry-run
```
or
```bash
sudo certbot renew -v
```
Then Restart nginx:
```bash
sudo systemctl restart nginx
```

## Check nginx configuration
```bash
sudo nginx -t
```
then:
```bash
sudo cat /etc/nginx/sites-enabled/default
```
(or your site's config)

## To Check nginx status
```bash
sudo systemctl status nginx
```

## Check that the domain points to this EC2
From your own computer, run:
```bash
nslookup api.purnawalla.com
```
or
```bash
ping api.purnawalla.com
```
It should resolve to:
```
98.130.82.165
```
Which is EC2 public IP

## Check the certificate paths in Nginx
Run:
```bash
sudo grep -R "ssl_certificate" /etc/nginx/sites-enabled/
```
and 
```bash
sudo grep -R "ssl_certificate_key" /etc/nginx/sites-enabled/
```
The output should point to:
/etc/letsencrypt/live/api.purnawalla.com/fullchain.pem
/etc/letsencrypt/live/api.purnawalla.com/privkey.pem
