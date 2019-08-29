# 29th of August 2019

## You can't rename an index in MariaDB 10.3
In Laravel, you're supposed to be able to call `$table->renameIndex()` inside a migration, but it doesn't work on MariaDB 10.3 since it hasn't supported index renaming yet.

# 28th of August 2019

## It's possible to expose local webserver to the Internet.
What you need to do is create an ssh tunnel using the command below:
```bash
ssh -R 9000:localhost:8000 user@server
```
The command above creates an ssh tunnel between your computer and the server, and maps the your computer's `localhost:9000` to the server's `localhost:8000`.


After that you only need to create a reverse proxy inside a server to point a domain (e.g. `tunnel.mydomain.com`) to your server's `localhost:9000` which has been previously mapped to your local computer's `localhost:8000`. Assuming you have a some kind of a web service running your local computer's `localhost:8000`, you now can access that service from other computers through `tunnel.mydomain.com`.
