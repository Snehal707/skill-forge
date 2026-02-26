---
name: nginx-web-server-setup
description: Install and configure nginx as a basic web server to serve static content
version: 1.0.0
metadata:
  skill_forge:
    domain: "nginx"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
  hermes:
    tags: [nginx, web-server, http, static-content]
    category: web-development
---

# nginx Web Server Setup

## When to Use
When you need to serve static HTML files, CSS, JavaScript, or other web content with high performance and low resource usage.

## Prerequisites
- Ubuntu/Debian-based system with sudo access
- Basic knowledge of command line
- Domain name or public IP address (optional)

## Procedure
1. Update package repositories: `sudo apt update`
2. Install nginx: `sudo apt install nginx -y`
3. Start nginx service: `sudo systemctl start nginx`
4. Enable nginx to start on boot: `sudo systemctl enable nginx`
5. Check nginx status: `sudo systemctl status nginx`
6. Create your web content directory: `sudo mkdir -p /var/www/your-domain`
7. Set proper ownership: `sudo chown -R $USER:$USER /var/www/your-domain`
8. Set directory permissions: `sudo chmod -R 755 /var/www/your-domain`
9. Create a simple index.html: `echo '<h1>Welcome to nginx!</h1>' > /var/www/your-domain/index.html`
10. Create server block configuration: `sudo nano /etc/nginx/sites-available/your-domain`
11. Add basic server configuration block with root directory and server_name
12. Enable the site: `sudo ln -s /etc/nginx/sites-available/your-domain /etc/nginx/sites-enabled/`
13. Test nginx configuration: `sudo nginx -t`
14. Reload nginx: `sudo systemctl reload nginx`

## Verification
- Open web browser and navigate to your server's IP address or domain
- Confirm "Welcome to nginx!" message displays
- Check nginx is running: `sudo systemctl is-active nginx`
- Verify port 80 is listening: `sudo netstat -tlnp | grep :80`

## Pitfalls
- Firewall may block port 80/443 - configure ufw or iptables accordingly
- SELinux on CentOS/RHEL may prevent nginx from serving files
- Incorrect file permissions can cause 403 Forbidden errors
- Syntax errors in configuration files will prevent nginx from starting

## Sources
- https://nginx.org/
- https://www.f5.com/products/nginx
- https://github.com/nginx/nginx
- https://en.wikipedia.org/wiki/Nginx
- https://www.reddit.com/r/nginx/comments/mvatwk/what_is_nginx_explain_to_me_like_im_5_because_im/