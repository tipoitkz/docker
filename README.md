# schemaspy

```bash
docker build --tag schemaspy:1.0 .

docker run -v /tmp/output:/schemaspy/output --rm schemaspy:1.0 -host 192.168.0.81 -port 5432 -u user -p 'password' -db dbName -schemas schema1, schema2 -t pgsql11
```
