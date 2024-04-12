<p align="center"><img alt="Directus Logo" src="https://user-images.githubusercontent.com/522079/158864859-0fbeae62-9d7a-4619-b35e-f8fa5f68e0c8.png"></p>

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
6. Bootstrap the database:

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

### Initialize the database

Either install the database (if it's empty) or migrate it to the latest version (if it already exists and has missing migrations).

```sh
pnpm bootstrap
```

### Update the database

```sh
pnpm migrate
```

### Generate app key and secret

```sh
npx directus security key:generate
npx directus security secret:generate
```

Copy and paste the output in your `.env` file.

## Deployment

> Tip: If you're using Directus in production, it's recommended to lock the version of Directus in your package.json because things might break when this package gets updated.

Example:
```diff
"dependencies": {
-  "directus": "^10.0.0"
+  "directus": "10.0.0"
}
```
