# docker-prestashop

## Description

The function of this repository is to set up a plugin development environment on the Prestashop platform.

## Setup

### Automated Setup (New Project)

```bash
# Create your project directory then go into it:
mkdir ~/Projects/docker-prestashop
cd $_

# Run this automated one-liner from the directory you want to install your project.
curl -s https://raw.githubusercontent.com/PluginAndPartners/docker-prestashop/main/lib/onelinesetup | bash -s 
```

### Manual Setup (New Project)

Clone the repository
```bash
git clone git@github.com:PluginAndPartners/docker-prestashop.git
```

In the project folder, run the script that goes up the entire environment and configures SSL certificate and configures prestashop
```bash
bash bin/setup
```

## Install Mercado Pago Plugin

Execute the install script 
```bash
bash bin/install_plugin
```

This will show up
```
Você deseja instalar o plugin do Mercado Pago direto da loja?
1) Sim, quero a ultima versão do plugin
2) Sim, a versão que estou desenvolvendo
3) Não
```

### First option
If you choose the **first option**, the script will go to the prestashop marketplace and install the last version o plugin.

### Second option
if you choose the **second option**, this will show up:
```
Por favor, coloque o caminho da pasta do seu plugin (por exemplo: /Users/mgouveia/Projects/cart-prestashop):
```
Put the path of the plugin, in this case **cart-prestashop**

### Third option
Do nothing




## Uninstall Mercado Pago Plugin
Execute the uninstall script 
```bash
bash bin/uninstall_plugin
```

## Scripts Available
- `bin/setup` Raises the entire structure and creates the SSL certificate to be used. Installs Prestashop.

[**All scripts below depend on the environment being already configured**]

- `bin/run` Start all containers, good practice to use this instead of `docker-compose up -d`, as it may contain additional helpers.
- `bin/stop` Stop all containers, good practice to use this instead of `docker-compose down -d`, as it may contain additional helpers.
- `bin/ssl` Create SSL certificate to be used in the project.
- `bin/configure_prestashop` Installs Prestashop.
- `bin/configure_nginx` Configure Nginx to works with Prestashop
- `bin/install_plugin` Set up a setup for installing the Mercado Pago plugin.
- `bin/sync` When passing the path of the plugin folder of Mercado Pago, it installs that version inside the project.
- `bin/remove` **[CAUTION]** Erases the entire project that was inside the containers, including the database. Drop all containers.

## Todo
To improve this project, I list some things:
- [ ] Pre-registered products
- [ ] Choosing which version of prestashop to install
- [ ] Choosing which version of Prestashop to install
- [ ] Choosing which version of PHP to install
- [ ] Configure an FTP server to perform functions they need (Installing plugins)