# goodhouseinc.com

Personal landing page for Chris Gilpin (Good House Inc.).

## Live

Hosted on the shared Hetzner box (`49.12.213.190`, hostname `mk-track-editor`):

- Files: `/var/www/goodhouseinc`
- Nginx: `/etc/nginx/sites-available/goodhouseinc`
- Domains: `goodhouseinc.com`, `www.goodhouseinc.com`

## Deploy

From a machine with the Hetzner SSH key:

```bash
scp index.html styles.css hetzner:/var/www/goodhouseinc/
# or from this box:
# scp -o BatchMode=yes index.html styles.css hetzner:/var/www/goodhouseinc/
```

After DNS points at the server, issue TLS once:

```bash
ssh hetzner 'certbot --nginx -d goodhouseinc.com -d www.goodhouseinc.com --non-interactive --agree-tos -m gilpin@mac.com --redirect'
```

## DNS (needed for public + HTTPS)

At the registrar for `goodhouseinc.com`:

| Type | Name | Value |
|------|------|--------|
| A    | `@`  | `49.12.213.190` |
| A    | `www`| `49.12.213.190` |

Keep existing records for `007` and `trackeditor` as they are.

## Local preview

Open `index.html` in a browser, or:

```bash
python3 -m http.server 8080
```
