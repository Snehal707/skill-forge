```markdown
---
name: nginx-basic-setup
description: Install and configure nginx as a web server with basic virtual hosts
version: 1.0.0
metadata:
  skill_forge:
    domain: "nginx"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
  hermes:
    tags: [nginx, web-server, http, proxy, devops]
    category: devops
---

# Basic NGINX Setup and Configuration

## When to Use
- Need to serve static websites or web applications
- Setting up a reverse proxy for backend services
- Configuring load balancing between multiple servers
- Implementing SSL/TLS termination

## Prerequisites
- Linux/Unix system with sudo privileges
- Basic command line knowledge
- Domain name or IP address for configuration

## Procedure
1. Install nginx: `sudo apt update && sudo apt install nginx -y` (Ubuntu/Debian) or `sudo yum install nginx -y` (RHEL/CentOS)
2. Start and enable nginx service: `sudo systemctl start nginx && sudo systemctl enable nginx`
3. Verify installation: `sudo systemctl status nginx`
4. Test default page: `curl localhost` or visit `http://your-server-ip`
5. Create basic virtual host configuration: `sudo nano /etc/nginx/sites-available/mysite.conf`
6. Add basic server block:
   ```
   server {
       listen 80;
       server_name example.com www.example.com;
       root /var/www/mysite;
       index index.html;
       
       location / {
           try_files $uri $uri/ =404;
       }
   }
   ```
7. Create web directory: `sudo mkdir -p /var/www/mysite`
8. Create test page: `echo "<h1>My NGINX Site</h1>" | sudo tee /var/www/mysite/index.html`
9. Enable site: `sudo ln -s /etc/nginx/sites-available/mysite.conf /etc/nginx/sites-enabled/`
10. Test configuration: `sudo nginx -t`
11. Reload nginx: `sudo systemctl reload nginx`

## Verification
- Check nginx status: `sudo systemctl status nginx`
- Verify configuration syntax: `sudo nginx -t`
- Test site response: `curl -H "Host: example.com" localhost`
- Check error logs if issues: `sudo tail -f /var/log/nginx/error.log`

## Pitfalls
- Forgetting to test configuration before reloading can break service
- Incorrect file permissions on web directory (use `sudo chown -R www-data:www-data /var/www/mysite`)
- Firewall blocking port 80/443 (check with `sudo ufw status`)
- Conflicting server blocks with same server_name

## Sources
- https://nginx.org/
- https://nginx.org/en/docs/beginners_guide.html
- https://github.com/nginx/nginx
- https://en.wikipedia.org/wiki/Nginx
- https://www.f5.com/products/nginx
```