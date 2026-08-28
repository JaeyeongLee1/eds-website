# Engineering Data Science Lab Website

Production repository for the Engineering Data Science Lab website, owned by the `kaist-eds-lab` GitHub Organization.

The site was migrated from the earlier design prototype into a maintainable, data-driven structure intended for long-term lab ownership.

## Operating principle

- Factual content is stored separately from presentation code.
- Routine updates should not require editing HTML or CSS.
- Professor/member/publication/alumni updates are managed through structured data and Pages CMS.
- AI assistants should follow `AGENTS.md` before changing site content.
- Repository ownership is separated from any single lab member's personal GitHub account.

## Deployment

- Hosting: GitHub Pages
- Production domain: `https://eds.kaist.ac.kr`
- DNS target for the custom subdomain: `kaist-eds-lab.github.io`
- Custom-domain declaration: root `CNAME` file

The GitHub-side configuration is ready for the custom domain. The KAIST DNS record must point `eds.kaist.ac.kr` to `kaist-eds-lab.github.io` for the production domain to resolve to this site.
