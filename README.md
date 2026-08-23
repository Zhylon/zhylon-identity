# Zhylon Identity

Convenience meta-package. Pulls in both:

- [`zhylon/zhylon-auth`](https://github.com/zhylon/zhylon-auth) — "Login with ZhylonID" (Socialite-compatible OAuth2 for end users)
- [`zhylon/zhylonid-service`](https://github.com/zhylon/zhylonid-service) — server-to-server ZhylonID API client (`userExists()`, ecosystem user sync)

```bash
composer require zhylon/zhylon-identity
```

is equivalent to:

```bash
composer require zhylon/zhylon-auth zhylon/zhylonid-service
```

## When to use this vs. the individual packages

Most Zhylon products that offer "Login with ZhylonID" also need to check user existence
and sync users — that's the common case this package targets.

Install the individual packages directly instead if you only need one:

- Only SSO login, no server-to-server API calls → `zhylon/zhylon-auth` alone
- A backend-only service with no end-user login (e.g. an internal cron job or worker
  node) → `zhylon/zhylonid-service` alone

## Versioning

This package has no code and no autoloading of its own — it only declares version
constraints on the two real packages. Bump its own version when you want to publish a
new *recommended combination* (e.g. after a major release of either dependency), not on
every change to either package individually.

