# Domain Configuration

## GitHub Pages

We deploy from a branch `main`, folder `/docs`.

**Important:** do not enforce https on GitHub Pages for the custom domain configuration. This will break the `curl` command in the `gitprompt.sh` script because curl does not follow redirects for https requests by default.

The suffix `gitprompt.sh` will be added automatically, meaning just leave HOST empty for A and AAAA records and use `www` for CNAME records.

| Type  | Host | Value | TTL |
| ----- | ---- | ----- | --- |
| A | gitprompt.sh | 185.199.108.153 | 600 |
| A | gitprompt.sh | 185.199.109.153 | 600 |
| A | gitprompt.sh | 185.199.110.153 | 600 |
| A | gitprompt.sh | 185.199.111.153 | 600 |
| AAAA | gitprompt.sh | 2606:50c0:8000::153 | 600 |
| AAAA | gitprompt.sh | 2606:50c0:8001::153 | 600 |
| AAAA | gitprompt.sh | 2606:50c0:8002::153 | 600 |
| AAAA | gitprompt.sh | 2606:50c0:8003::153 | 600 |
| CNAME | www.gitprompt.sh | danieldietrich.github.io | 600 |

See [Using an apex domain for your GitHub Pages site](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages#using-an-apex-domain-for-your-github-pages-site) for details.

## Verification

The suffix `gitprompt.sh` will be added automatically, meaning just leave HOST empty for the TXT record and use `_github-pages-challenge-USERNAME`.

| Type  | Host | Value | TTL |
| ----- | ---- | ----- | --- |
| TXT | _github-pages-challenge-danieldietrich.gitprompt.sh | `<CODE-BY-GITHUB>` | 600 |

See [Verifying your custom domain for GitHub Pages](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages) for details.
