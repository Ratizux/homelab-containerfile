No Containerfile required (at least for now).

```
podman pod create -p 7707:80 postgres
```

```
podman create --name postgresql -e POSTGRES_PASSWORD=[Password] --pod postgres postgres
```

```
podman create --name pgadmin -e PGADMIN_DEFAULT_EMAIL=[Email] -e PGADMIN_DEFAULT_PASSWORD=[Password] --pod postgres pgadmin4
```

Privileged account `postgres` is used here because this configuration is indented for learning basic feature of PostgreSQL.

Do NOT use this configuration for serious business.
