# Tech-Summit-Linux-Migration

A demonstration repository for Linux workload migration to Azure, featuring a PHP web application with PostgreSQL database backend.

## Overview

This repository contains resources for deploying and migrating a sample on-premises Linux workload to Azure. It includes:

- **Web Application**: A PHP-based order management system that displays order details from a PostgreSQL database
- **Database**: PostgreSQL database with Northwind sample data
- **Deployment Scripts**: Automated installation scripts for setting up both application and database servers

## Repository Structure

```
resources/
└── deployment/
    └── onprem/
        ├── webapp/
        │   └── orders.php           # PHP web application
        ├── database/
        │   └── northwind.sql        # PostgreSQL database schema and data
        ├── APP-workload-install.sh  # Application server setup script
        └── PG-workload-install.sh   # PostgreSQL server setup script
```

## Components

### Web Application (orders.php)

A PHP application that:
- Connects to a PostgreSQL database
- Displays order details from the Northwind database
- Shows server connection information
- Presents data in a formatted HTML table

### Database (northwind.sql)

The Northwind database includes:
- Multiple tables (orders, order_details, products, customers, employees, etc.)
- Sample data for testing and demonstration
- Foreign key relationships and constraints

### Installation Scripts

#### PostgreSQL Server Setup (PG-workload-install.sh)

Automates the installation and configuration of:
- PostgreSQL 16
- Database initialization
- User creation (demouser, rootuser)
- Database and tablespace setup
- Firewall configuration
- Data import from northwind.sql

#### Application Server Setup (APP-workload-install.sh)

Automates the installation and configuration of:
- Apache HTTP Server
- PHP and PostgreSQL PHP extension
- Firewall rules for HTTP/HTTPS
- SELinux configuration
- Web application deployment

## Usage

### Setting up the PostgreSQL Server

```bash
# Clone the repository
git clone https://github.com/cassiekays/Tech-Summit-Linux-Migration.git

# Run the PostgreSQL installation script
cd Tech-Summit-Linux-Migration
sudo bash resources/deployment/onprem/PG-workload-install.sh
```

### Setting up the Application Server

```bash
# Run the application server installation script
sudo bash resources/deployment/onprem/APP-workload-install.sh
```

### Accessing the Application

After installation, access the web application at:
```
http://<server-ip>/orders.php
```

## Database Configuration

The default database configuration is:
- **Host**: 10.0.0.4
- **Port**: 5432
- **Database**: northwind
- **User**: demouser
- **Password**: demopass123

To modify the database connection, edit the configuration in `resources/deployment/onprem/webapp/orders.php`.

## Requirements

- Red Hat Enterprise Linux (RHEL) or compatible distribution
- Root or sudo access
- Internet connectivity for package installation

## License

This project is provided as-is for demonstration and educational purposes.