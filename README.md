# Service Access Database

Database schema and migration source of truth for the Access Control domain.

## Table of Contents

- [Overview](#overview)
- [Database Schema](#database-schema)
- [Migration Structure](#migration-structure)
- [Environment Variables](#environment-variables)
- [Running Liquibase](#running-liquibase)

## Overview

This repository contains the database schema and migration scripts for the Service Access domain. It is used as the source of truth for the database schema and migration scripts.

## Database Schema

```mermaid
erDiagram

```

## Migration Structure

The migrations are managed via **Liquibase** and are located in the `changes/` directory.
The execution order is defined in `master.yml`.

| File                               | Description                                       | ID Prefix |
| :--------------------------------- | :------------------------------------------------ | :-------- |
| `001-create-permission-tables.yml` | Creates `permission` and `permission_pin` tables. | `001-XX`  |

## Environment Variables

The following environment variables are required to run Liquibase (or provided via `.env`):

- `DATABASE_URL`: The URL of the database to connect to (e.g. `jdbc:postgresql://host:port/db`).
- `DATABASE_USER`: The username to use when connecting to the database.
- `DATABASE_PASSWORD`: The password to use when connecting to the database.

## Running Liquibase

You can use the provided `Makefile` or run via docker:

```bash
# Check status
make status

# Run update (apply migrations)
make update
```
