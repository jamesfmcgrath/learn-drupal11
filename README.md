# Drupal 11 Learning & Experimentation

A Drupal 11 site for learning and experimenting with Drupal features, modules, and development workflows.

## Overview

This project serves as a sandbox environment for exploring Drupal 11 capabilities, testing new features, and practicing Drupal development techniques.

## Local Development

This project uses [Lando](https://lando.dev/) for local development.

### Prerequisites

- [Lando](https://lando.dev/download/) installed on your system
- Docker Desktop (required by Lando)

### Getting Started

1. **Clone the repository**

   ```bash
   git clone https://github.com/jamesfmcgrath/learn-drupal11.git
   cd learn-drupal11
   ```

2. **Start Lando**

   ```bash
   lando start
   ```

3. **Install dependencies**

   ```bash
   lando composer install
   ```

4. **Install Drupal** (if not already installed)
   ```bash
   lando drush site:install --account-name=admin --account-pass=admin -y
   ```

### Common Commands

- **Start the site**: `lando start`
- **Stop the site**: `lando stop`
- **Rebuild Lando**: `lando rebuild -y`
- **Access the site**: Check `lando info` for the URL (typically `https://learn-drupal11.lndo.site`)
- **Run Drush commands**: `lando drush [command]`
- **Run Composer commands**: `lando composer [command]`
- **Clear cache**: `lando drush cr`
- **Database import**: `lando db-import database.sql`
- **Database export**: `lando db-export database.sql`

### Development Services

The Lando environment includes several helpful services:

- **MailHog**: Email testing - [https://mail.learn-drupal11.lndo.site](https://mail.learn-drupal11.lndo.site)
  - Catches all emails sent from Drupal
  - No emails sent to real addresses
- **Adminer**: Database management GUI - [https://adminer.learn-drupal11.lndo.site](https://adminer.learn-drupal11.lndo.site)
  - Visual database browser and editor
  - Credentials: `drupal11` / `drupal11` / `drupal11`
- **ChromeDriver**: Automated browser testing support
- **Node.js 20**: Frontend tooling and JavaScript development

### Debugging with Xdebug

Xdebug is available but disabled by default for performance:

- **Enable Xdebug**: `lando xdebug-on`
- **Disable Xdebug**: `lando xdebug-off`

Configure your IDE with:

- Server name: `appserver`
- Path mappings: Map your local project root to `/app`

### Code Quality Tools

- **PHP CodeSniffer**: `lando phpcs [path]` - Check coding standards
- **PHP Code Beautifier**: `lando phpcbf [path]` - Auto-fix coding standards
- **PHPStan**: `lando phpstan [options]` - Static analysis
- **PHPUnit**: `lando phpunit [options]` - Run tests

### Frontend Development

- **Install core frontend dependencies**: `lando install-frontend`
- **ESLint (JavaScript)**: `lando eslint-js [path]`
- **ESLint (YAML)**: `lando eslint-yml [path]`
- **Stylelint (CSS)**: `lando stylelint [path]`
- **Node/NPM**: `lando node` / `lando npm` / `lando yarn`

### Development Tools

The project includes several development tools accessible via Composer:

- **Drush**: `lando drush` - Drupal command-line tool
- **Drupal Code Generator**: `lando dcg` - Code scaffolding tool
- **Robo**: `lando robo` - Task runner
- **PsySH**: `lando psysh` - PHP REPL for debugging

## Project Structure

- `/web` - Drupal web root
- `/vendor` - Composer dependencies
- `/recipes` - Drupal recipes
- `composer.json` - PHP dependencies

## Learning Resources

- [Drupal 11 Documentation](https://www.drupal.org/docs/understanding-drupal/drupal-11)
- [Drupal API Reference](https://api.drupal.org/)
- [Lando Documentation](https://docs.lando.dev/)
- [Drush Commands](https://www.drush.org/latest/commands/all/)

## Notes

This is a personal learning environment. Feel free to experiment, break things, and learn from the process!

## License

This is a learning project and not intended for production use.
