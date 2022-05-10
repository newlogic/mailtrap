# Mailtrap Docker Image

Docker image to catch all emails and display them in a webmail interface. For development purposes only.

## Usage in Docker Compose

Add the following service to your `docker-compose.yml`:

```
  mail:
    image: newlogic/mailtrap
    restart: unless-stopped
    ports:
     - 8080:80
```

This will enable services to:
 - send emails by connecting to the SMTP server with hostname `mail` and port `25`;
 - receive emails by connecting to the IMAP server with hostname `mail`, port `143`, username `mailtrap`, and password `mailtrap`.

Webmail interface is accessible at the following URL: http://localhost:8080

## Default login:

* **Username:** `mailtrap`
* **Password:** `mailtrap`

## Customisations:

Set environment variables

* `MT_USER` - mailbox user, default mailtrap
* `MT_PASSWD` - mailbox user password, default mailtrap
* `MT_MAILBOX_LIMIT` - mailbox limit in bytes, default 51200000
* `MT_MESSAGE_LIMIT` - message limit in bytes, default 10240000

## Build instructions

```
docker build -t newlogic/mailtrap .
```