# Custom domain names

You should use a custom domain for your hosted portal.  This can be either an *apex domain* (like `gbif.zz` and usually also `www.gbif.zz`) or a *subdomain* name (like `data.tecala.zz`, when your institution is `tecala.zz` or `www.tecala.zz`).

*If your IT department is going to handle everything, you needn't read any further — tell them the domain or subdomain and send them this page.*

If you want a new domain, you will need to register it. There is usually an annual fee for this, and it's important to make sure the fee will continue to be paid year after year – your IT department might be best to arrange this.

You will then need to set DNS records.  If you have registered a domain yourself, there is usually an option to configure DNS somewhere nearby.

## Apex domain (`gbif.zz` etc)

Some DNS providers support `ANAME` or `ALIAS` records.  If yours does, create an `ANAME` or `ALIAS` record for the apex domain (e.g. `gbif.zz`) to point to `hosted-portal.gbif.org`.

If your DNS provider does *not* support `ANAME` or `ALIAS` records, create an `A` record for the apex domain (e.g. `gbif.zz`) to point to `130.225.43.5`.

Either way, create a `CNAME` record for `www` (e.g. `www.gbif.zz`) to point to `hosted-portal.gbif.org`.

## Subdomains (`data.tecala.zz` etc)

Create a single `CNAME` record for your subdomain (e.g. `data.tecala.zz`) to point to `hosted-portal.gbif.org`.

GBIF will create a TLS certificate using LetsEncrypt.  This enables the site to work with secure "https://" connections.  Since your institution is probably already using a TLS certificate, it is a good idea to ensure GBIF has permission to do this.

Create a `CAA` record for the same subdomain (e.g. `data.tecala.zz`) with the value `CAA 0 issue "letsencrypt.org"`.

(The `CAA` record is optional, unless your organization already has a `CAA` record for e.g. `tecala.zz`, in which case it is required.  Some DNS providers don't support creating `CAA` records — then you can just ignore it.)

## Finally

Create an issue in the GitHub repository for your portal.  Write the domain (or subdomain), and assign it to MattBlissett, who will update GBIF's configuration to use the domain.
