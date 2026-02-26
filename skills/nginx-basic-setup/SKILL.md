---
name: nginx-basic-setup
description: Install and configure nginx as a basic web server with reverse proxy capabilities
version: 1.0.0
metadata:
  skill_forge:
    domain: "nginx"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
  hermes:
    tags: [nginx, web-server, reverse-proxy, load-balancer]
    category: devops
---

# nginx Basic Setup

## When to Use
When you need to set up a web server, reverse proxy, or load balancer for web applications.

## Prerequisites
- Ubuntu/Debian or CentOS/RHEL system with sudo access
- Basic understanding of web servers and HTTP

## Procedure
1. Update package manager: `sudo apt update` (Ubuntu/Debian) or `sudo yum update` (CentOS/RHEL)
2. Install nginx: `sudo apt install nginx` (Ubuntu/Debian) or `sudo yum install nginx` (CentOS/RHEL)
3. Start and enable nginx service: `sudo systemctl start nginx && sudo systemctl enable nginx`
4. Check nginx status: `sudo systemctl status nginx`
5. Configure firewall if needed: `sudo ufw allow 'Nginx Full'` (Ubuntu) or `sudo firewall-cmd --permanent --add-service=http && sudo firewall-cmd --reload` (CentOS)
6. Test default installation: Open browser and navigate to `http://your-server-ip`
7. Edit main configuration: `sudo nano /etc/nginx/nginx.conf`
8. Create custom site configuration: `sudo nano /etc/nginx/sites-available/mysite`
9. Enable site: `sudo ln -s /etc/nginx/sites-available/mysite /etc/nginx/sites-enabled/`
10. Test configuration: `sudo nginx -t`
11. Reload nginx: `sudo systemctl reload nginx`

## Verification
- Browser shows nginx welcome page at server IP
- `sudo nginx -t` returns "syntax is ok" and "test is successful"
- `curl -I http://your-server-ip` returns HTTP 200 status

## Pitfalls
- Forgetting to test configuration before reloading can break the service
- Port 80/443 might be blocked by firewall
- Configuration syntax errors will prevent nginx from starting
- Multiple server blocks with same server_name can cause conflicts

## Sources
- https://nginx.org/
- https://www.f5.com/products/nginx
- https://github.com/nginx/nginx
- https://en.wikipedia.org/wiki/Nginx
- https://www.reddit.com/r/nginx/comments/mvatwk/what_is_nginx_explain_to_me_like_im_5_because_im/