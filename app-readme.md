# Nginx Proxy Manager - Ingress Controller

## Overview

Nginx Proxy Manager is a pre-built Docker image that provides a powerful reverse proxy solution with SSL termination and an intuitive web-based management interface. **This chart is configured to act as your cluster's ingress controller**, exposing services directly on standard ports.

## Key Features

- **🌐 Ingress Controller**: Direct access on ports 80, 81, and 443 across all cluster nodes
- **🔒 Automatic SSL**: Let's Encrypt integration with automatic certificate generation and renewal
- **🎛️ Web-based Management**: Clean, intuitive interface for managing proxy hosts and SSL certificates
- **⚡ High Performance**: Built on Nginx for optimal performance and reliability
- **🔧 Advanced Configuration**: Support for custom Nginx configs and headers

## Quick Start

### Default Access Points
After deployment, the service is accessible on **any node IP** in your cluster:

- **HTTP Traffic**: `http://[any-node-ip]:80`
- **HTTPS Traffic**: `https://[any-node-ip]:443`
- **Admin Interface**: `http://[any-node-ip]:81`

### Default Admin Credentials
- **Email**: `admin@example.com`
- **Password**: `changeme`

**⚠️ SECURITY**: Change these credentials immediately after first login!

## Ingress Controller Setup

This Nginx Proxy Manager instance acts as your cluster's ingress controller:

1. **Configure Proxy Hosts**: Use the admin interface to create proxy rules
2. **SSL Management**: Enable Let's Encrypt for automatic SSL certificates
3. **Access Lists**: Set up authentication and IP restrictions as needed
4. **Custom Configs**: Add advanced Nginx configurations for specific requirements

## Storage Configuration

The chart creates persistent volumes for:
- **Application Data** (10Gi default): Configuration, database, and logs
- **SSL Certificates** (1Gi default): Let's Encrypt certificates and private keys

## Database Options

- **Built-in SQLite** (default): Zero-configuration, ready to use
- **External Database**: MySQL, MariaDB, or PostgreSQL for high-availability setups

## Security Best Practices

- Change default admin credentials on first login
- Use external database for production environments
- Configure proper firewall rules for exposed ports
- Review and update access lists regularly
- Enable fail2ban protection if available

## Support & Documentation

- **Project Homepage**: [nginxproxymanager.com](https://nginxproxymanager.com/)
- **GitHub Repository**: [nginx-proxy-manager/nginx-proxy-manager](https://github.com/NginxProxyManager/nginx-proxy-manager)
- **Documentation**: Built-in help available in the admin interface