# Keelo Modules

This repository serves as the official remote registry for reusable [Keelo](https://github.com/matansuliman/keelo) modules. 

Keelo allows you to compose infrastructure from these standardized blueprints instead of writing repetitive YAML.

## Available Modules

| Module | Description |
|---|---|
| [`base-postgres`](./base-postgres) | A highly-configurable PostgreSQL database module with persistent storage. |
| [`base-redis`](./base-redis) | A standard Redis cache module. |

## Usage

You can use these modules in any Keelo `project.yaml` using the shorthand resolution feature (assuming shorthand resolves to this repo, or using the full path).

### Example `project.yaml`

```yaml
project: my-app
modules:
  - name: db
    source: "git::https://github.com/matansuliman/keelo-modules//base-postgres"
    values:
      DB_NAME: "myapp_db"
      VERSION: "15-alpine"
      
  - name: cache
    source: "git::https://github.com/matansuliman/keelo-modules//base-redis"
```

## Contributing

1. **Branch off `dev`**: All new modules should be created on branches derived from `dev`. Do not branch from or merge directly to `main`.
2. **Module Structure**: 
   - A module is defined by a directory containing at least `module.yaml` and `compose.yaml.tmpl`.
3. **Pull Requests**: Submit PRs targeting the `dev` branch.
