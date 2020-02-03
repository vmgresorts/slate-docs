# Hosting

## Locally

> Example `.env` file (as of Feb 3rd, 2020)

```
ENVIRONMENT=development
BASE_URL=http://localhost/
MYSQL_DATABASE=**********
MYSQL_HOSTNAME=**********
MYSQL_USER=**********
MYSQL_PASSWORD=**********
DEV_KEY=(some random string)
SOCKET_KEY=(some random string)
```

> Log output if project successfully launches

```
Starting portal-react_monolith_1 ... done
Attaching to portal-react_monolith_1
monolith_1  | => Composing...
monolith_1  | Do not run Composer as root/super user! See https://getcomposer.org/root for details
monolith_1  | Loading composer repositories with package information
monolith_1  | Installing dependencies (including require-dev) from lock file
monolith_1  | Nothing to install or update
monolith_1  | Generating autoload files
monolith_1  | ocramius/package-versions: Generating version class...
monolith_1  | ocramius/package-versions: ...done generating version class
monolith_1  | => Generating proxies...
monolith_1  |
monolith_1  |  Processing entity "Abstracts\Image"
...
monolith_1  |  Processing entity "Entity\UnitImage"
monolith_1  |
monolith_1  |  Proxy classes generated to "/var/www/html/portal/application/models/Proxies"
monolith_1  | => Starting apache2...
monolith_1  | => Ready for connections
```

> Successful JSON output

```json
{
  "status": true,
  "code": 200,
  "message": "🏓 pong!",
  "k8s-host": "a0afedda846b",
  "url": "http://localhost/",
  "_environment": "development",
  "_dev_database": true
}
```

<aside class='warning'>
You must have Docker Desktop installed and running before attempting to bring the project online.
</aside>

### Hosting locally with Docker

1. Ensure your repository is cloned and up to date
2. Create the required environment files. Unless you're working on a legacy branch, the only thing you have to do is create an `.env` file in the project root. See the example.
3. Open your CLI and run `docker-compose up`. It will take a moment to install dependencies and build the project.
4. You should see output that resembles the "Log output" example. If you do not, a step may have been followed incorrectly or something else is interfering with docker.
5. Navigate to `http://localhost/`. You should see JSON output that indicates you've hit the API.

### Troubleshooting Docker

1. This is a rare issue, but ensure that `/monolith/entrypoint.sh` has `LF` and not `CRLF` End of Line sequences. This will sometimes prevent Docker from launching the project.
2. Ensure you have up-to-date credentials entered in Docker Desktop's settings. You will receive errors that prevent the project from launching if you do not.

For other issues, speak with whoever is currently maintaining the project.
