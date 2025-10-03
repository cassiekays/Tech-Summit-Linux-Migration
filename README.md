# Tech-Summit-Linux-Migration

## Skip exercise 00

> [!IMPORTANT]  
>
> - VM resources are already created on-prem
> - Pre-migration application testing results in error due to old infrastructure

## Migrate the PostgreSQL DB to Azure

> [!TIP]  
> Refer to Database team's instructions [here](https://microsoft.github.io/TechExcel-Migrate-Linux-workloads/docs/01_migrate_postgresql_db/01_migrate_postgresql_db.html).

## Migrate App to App Service

### Create app service plan and app service in Azure

> [!TIP]  
> Leverage the skeleton [here](https://microsoft.github.io/TechExcel-Migrate-Linux-workloads/docs/02_migrate_web_app/02_03.html) as well.

- Standard S1
- Linux
- PHP 8.3

```CLI
Azure CLI commands to go here
```

```SQL
PSQL credentials

dvdrental
pgadmin
pgadmin123
```

```bash
apt-get update
apt install git-all -y
git clone https://github.com/microsoft/TechExcel-Migrate-Linux-workloads.git
# mkdir site && cd site
# mkdir wwwroot && cd wwwroot
# touch actors.php
cp https://github.com/cassiekays/Tech-Summit-Linux-Migration/blob/actors/actors.php actors.php
nano site/wwwroot/actors.php
```
