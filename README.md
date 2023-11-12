![Banner](https://user-images.githubusercontent.com/522079/158864859-0fbeae62-9d7a-4619-b35e-f8fa5f68e0c8.png)

## Requirements

- Node.js `v18.x`
- pnpm `v8.x`
- MySQL `v2.x`

## Getting Started

1. Install Node.js dependencies:

```sh
pnpm install
```

2. Create a copy of the `.env.example` file and rename it to `.env`.
3. Generate app key and secret:

```sh
pnpm security
```

4. Assign the generated strings to the key and secret variable inside the `.env` file.
5. If you're using MySQL:
   1. Create a fresh new database.
   2. Change the database credentials in the `.env` file.
6. If you're using SQLite, then a new `data.db` file will be created when running the next command.
7. Bootstrap the database:

```sh
pnpm bootstrap
```

8. Start Directus:

```sh
pnpm start
```

9. Open http://localhost:8055 in your browser.
10. Log in with the credentials of `ADMIN_EMAIL` and `ADMIN_PASSWORD` found at the end of the `.env` file.

## Directus Commands

### Run an instance

```sh
pnpm start
```

### Debug an instance

This useful when developing extensions.

```sh
pnpm debug
```

### Initialize the database

Either install the database (if it's empty) or migrate it to the latest version (if it already exists and has missing migrations).

```sh
pnpm bootstrap
```

### Update the database

```sh
pnpm db:update
```

### Generate app key and secret

```sh
pnpm security
```

This will place the generated strings at the end of the `.env` file.

## Scaffold folders

Run this command if you want to scaffold the default Directus folders.

```sh
mkdir uploads extensions extensions/displays extensions/endpoints extensions/hooks extensions/interfaces extensions/layouts extensions/modules extensions/operations extensions/panels
```

## Deployment

> Tip: If you're using Directus in production, it's recommended to lock the version of Directus in your package.json because things might break when this package gets updated.

Example:
```diff
"dependencies": {
-  "directus": "^9.20.0"
+  "directus": "9.20.0"
}
```

## SMTP

You can use [Ethereal](https://ethereal.email) (fake SMTP service) to setup email support.

### SMTP configuration

- Host: smtp.ethereal.email
- Port: 587
- Security: STARTTLS

### IMAP configuration

- Host: imap.ethereal.email
- Port: 993
- Security:	TLS

### POP3 configuration

- Host: pop3.ethereal.email
- Port: 995
- Security:	TLS
