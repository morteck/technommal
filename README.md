# LAMP Script to setup website domain!

This Bash script automates the installation and configuration of a WordPress website on a *nix server. It sets up a LAMP stack, configures WordPress, and handles domain/DNS settings with automatic SSL setup. The script is designed to work with most cloud servers, but it can be adapted for other hosting environments such as bare metal or local installations.

Features

LAMP Stack Installation: Installs Apache, MariaDB, PHP, and other required packages.

WordPress Installation: Automatically installs and configures WordPress with custom settings (site title, admin user, database, passwords, etc.).

Domain Configuration: Automatically updates DNS records (In my case I'm using the Linode API).

Secure SSH Setup: Configures a limited sudo user and disables root SSH access (this is optional).

SSL Configuration: Automatically installs a free SSL certificate using Certbot.

Firewall Configuration: Opens necessary firewall ports for HTTP, HTTPS, and email services.

Automation: Sets up cron jobs to keep WordPress updated automatically. Yay for unnattended upgrades!

Prerequisites

A Linode server or a similar Linux-based VPS.

A Linode API token for DNS record management.

A custom domain (e.g., technomammal.net) and access to its DNS settings.

A subdomain (e.g., www.technomammal.net) to point to the server.

Email access for the admin and SOA (Start of Authority) records.

Script Customization

Before running the script, modify the following variables to suit your environment:

# WordPress Settings
SITE_TITLE="site-title-here"
WP_ADMIN="adminuser"
WP_PASSWORD="user-passwd"
SOA_EMAIL_ADDRESS="email@domain.com"
DBROOT_PASSWORD="user-passwd"
DB_PASSWORD="user-passwd"

# Linode/SSH Security Settings
USER_NAME="administrator"
USER_PASSWORD="user-passwd"
DISABLE_ROOT="No"  # Options: Yes, No

# Domain Settings
LINODE_API_TOKEN="6ee57a2aa6095f9d285d71a0472107a05c465d26XXXXXXXXXXXXXXXXXXXXXXXX"
SUBDOMAIN="www" (or @ if so chosen)
DOMAIN="websitedomain.net" (Insert your owned dowmain name here)

# SSL Email Address
SOA_EMAIL_ADDRESS="zentech.computing@gmail.com"
