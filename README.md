# goodhouseinc.com

Personal landing page for Chris Gilpin / Good House Inc.

## Local

Open `index.html` in a browser, or:

```bash
npx serve .
```

## Deploy (Vercel)

```bash
npx vercel --prod
```

Then in the Vercel project, add domains `goodhouseinc.com` and `www.goodhouseinc.com`.

## DNS

Point the domain at Vercel (replace with the values Vercel shows if they differ):

**Apex (`goodhouseinc.com`)**
- Type: `A`
- Name: `@`
- Value: `76.76.21.21`

**WWW (`www.goodhouseinc.com`)**
- Type: `CNAME`
- Name: `www`
- Value: `cname.vercel-dns.com`

After DNS propagates, both `https://goodhouseinc.com` and `https://www.goodhouseinc.com` should serve this site.
