## CLOUDFLARE-NOTES

### Generate HTTPS (SSL/TLS) like Letsencrypt
1. SSL/TLS -> Origin Server -> Click Create Certificate
```
a. Provide the Host Names (your domains and sub domains) the click Create
b. Copy the Origin Certificate and Private Key in your VPS/Webhosting
```
2. In Ubuntu
```
    Origin Certificate -> /etc/cloudflare_ssl/cert.pem
    Private Key        -> /etc/cloudflare_ssl/key.pem    
```
3. In NGINX
```
ssl_certificate /etc/cloudflare_ssl/cert.pem;
ssl_certificate_key /etc/cloudflare_ssl/key.pem;
```
