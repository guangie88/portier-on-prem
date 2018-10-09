# Portier on Premise

Test docker-compose set-up to show passwordless login to web application via
Portier.

## Requirements

- Docker
- `docker-compose`

## Set-up

Simply run:

```bash
docker-compose up -d
```

This brings up the following services:

- `redis`, required by Portier to prevent timing attacks
- `mailhog`, a testing SMTP service with web UI to receive emails for the magic
  links
- `portier-broker`, reference implementation for Portier protocol to perform
  passwordless logins
- `porter-rp`, a testing Relying Party web application to demo the passwordless
  login. This represents your client web application that uses Portier for the
  passwordless login.

To test out the demo, open your web browser and navigate to
`http://localhost:8000`.

Enter any email address; dummy addresses work just as fine.

Next navigate to `http://localhost:8025` and find the email with the magic link.
Click on the magic link to perform the passwordless login.

If everything works fine, you should now be redirected back to `localhost:8000`
with a verified login.
