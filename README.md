## CLOUDFLARE-NOTES
### Go to your Site
1. Websites
### Setup CloudFlare DNS Record and (Name Server (NS) and A Record)
1. In CloudFlare -> DNS -> Records
```
Copy the CloudFlare Name Servers 
```
2. In NameCheap -> Domain List -> Domain
```
Paste the CloudFlare Name Servers in Name Cheap -> Name Servers -> Custom DNS
```
3. In CloudFlare -> DNS -> Records
```
Add Record your subdomains and other domains if not detected in the Table
```
### Generate HTTPS (SSL/TLS) like Letsencrypt
1. In CloudFlare -> SSL/TLS -> Origin Server -> Click Create Certificate
```
a. Provide the Host Names (your domains and sub domains) then click Create
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
### DNSSEC 
```
Add layer of security to your DNS to prevent fraudlent DNS and provide authenticity of DNS data
```
1. In CloudFlare -> DNS -> Settings -> Enable DNSSEC
```
Copy the -> Key Tag | Algorithm | Digest Type | Digest
```
2. In NameCheap -> Domain List -> Advanced DNS -> DNSSEC
```
Add new DS and Paste the -> Key Tag | Algorithm | Digest Type | Digest 
```
### References
[NameCheap CloudFlare](https://www.namecheap.com/support/knowledgebase/article.aspx/9607/2210/how-to-set-up-dns-records-for-your-domain-in-cloudflare-account/)

[Setup Website SSL and DNSSEC](https://medium.com/@johnmark_76235/setup-website-ssl-and-dnssec-of-cloudflare-and-namecheap-f3ac7f6fbd6d)
