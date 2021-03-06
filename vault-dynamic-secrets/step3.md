Let's connect to the `postgres` container.

```
docker exec -it postgres bash
```{{execute T1}}

Start the PostgreSQL client CLI.

```
psql -U root
```{{execute T1}}

Once you are in `psql`, execute `\du`{{execute T1}} to list users. You should find the Vault generated usernames.

**Example:**

```
root=# \du
                                                       List of roles
                    Role name                     |                         Attributes                         | Member of
--------------------------------------------------+------------------------------------------------------------+-----------
 root                                             | Superuser, Create role, Create DB, Replication, Bypass RLS | {}
 v-token-readonly-P4Rkmg3EUiqd6hNV5qNq-1589070089 | Password valid until 2020-05-10 01:21:34+00                | {}
 v-token-readonly-QBQAY9x6jMrNU13T4BH5-1589069184 | Password valid until 2020-05-10 01:06:29+00                | {}
```

Enter `\q`{{execute T1}} to quite the psql. Finally, enter `exit`{{execute T1}} to exit out of the Docker container shell.
