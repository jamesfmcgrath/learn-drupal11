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
- **Access the site**: Check `lando info` for the URL (typically `https://drupal11.lndo.site`)
- **Run Drush commands**: `lando drush [command]`
- **Run Composer commands**: `lando composer [command]`
- **Clear cache**: `lando drush cr`
- **Database import**: `lando db-import database.sql`
- **Database export**: `lando db-export database.sql`

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
