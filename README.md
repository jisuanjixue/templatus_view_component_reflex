[![Build Status](https://github.com/templatus/templatus_view_component_reflex/workflows/CI/badge.svg)](https://github.com/templatus/templatus_view_component_reflex/actions)
[![Cypress](https://img.shields.io/endpoint?url=https://dashboard.cypress.io/badge/simple/5d6bqs&style=flat-square&logo=cypress)](https://dashboard.cypress.io/projects/5d6bqs/runs)

# Templatus (view_component_reflex edition)

Templatus is an opinionated template to build web applications with Ruby on Rails and view_component_reflex. It simplifies the process of setting up a new application while following best practices.

Live demo available at

### Backend

- [Ruby](https://www.ruby-lang.org/de/) 3.2.0
- [Ruby on Rails](https://rubyonrails.org/) 7.0.4
- [ActionCable](https://guides.rubyonrails.org/action_cable_overview.html) for WebSocket communication
- [PostgreSQL](https://www.postgresql.org/) for using as SQL database
- [Sidekiq](https://sidekiq.org/) for background processing
- [Redis](https://redis.io/) for Caching, ActionCable, and Sidekiq

### Frontend

- [view_component_reflex](https://github.com/joshleblanc/view_component_reflex) for About Call component methods right from your markup, It builds upon stimulus_reflex and view_component:
- [ViewComponent](https://viewcomponent.org/) for creating reusable, testable & encapsulated view components
- [stimulus_reflex](https://docs.stimulusreflex.com/) for build reactive applications with the Rails tooling you already know and love
- [Slim](http://slim-lang.com/) for writing templates instead of ERB
- [Tailwind CSS 3](https://tailwindcss.com/) to not have to write CSS at all
- [Heroicons](https://heroicons.com/) for beautiful hand-crafted SVG icons
- [Vite](https://vitejs.dev/) for bundling JavaScript and CSS with Hot Module Replacement (HMR) in development

### Development

- [Puma-dev](https://github.com/puma/puma-dev) for using .test-domain and HTTPS in development
- [Foreman](https://github.com/ddollar/foreman) for starting up the application locally
- [dotenv](https://github.com/bkeepers/dotenv) to load environment variables from .env into ENV
- [Prettier](https://prettier.io/) for auto-formatting JavaScript and Ruby code in Visual Studio Code
- [Lookbook](https://github.com/allmarkedup/lookbook) as development UI for ViewComponent
- Live reloading

### Linting and testing

- [RuboCop](https://rubocop.org/) for Ruby static code analysis
- [ESLint](https://eslint.org/) for JavaScript static code analysis
- [RSpec](https://rspec.info/) for Ruby testing
- [Factory Bot](https://github.com/thoughtbot/factory_bot) for setting up Ruby objects as test data
- [Cypress](https://www.cypress.io/) for E2E testing

### Deployment

- [Docker](https://www.docker.com/) for production deployment, NOT for development
- [DockerRailsBase](https://github.com/ledermann/docker-rails-base) for fast building an optimized Docker image based on Alpine Linux
- [GitHub Actions](https://docs.github.com/en/actions) for testing, linting, and building Docker image
- [Dependabot](https://docs.github.com/en/code-security/supply-chain-security/keeping-your-dependencies-updated-automatically/about-dependabot-version-updates) configuration for updating dependencies (with auto-merge)
- Ready for serving assets via CDN like CloudFront
- [Honeybadger](https://www.honeybadger.io/) for error tracking in Ruby and JavaScript
- [Plausible](https://plausible.io/) for privacy friendly analytics
- [Lockup](https://lockup.interdiscipline.com/) to place a staging server behind a basic codeword

### Production

- [Lograge](https://github.com/roidrage/lograge) for single-line logging
- Gzip and Brotli compression of dynamic responses (HTML, JSON) using [Rack::Deflater](https://github.com/rack/rack/blob/master/lib/rack/deflater.rb), [Rack::Brotli](https://github.com/marcotc/rack-brotli)
- Fine-tuned Content Security Policy (CSP)
- Ready for PWA (manifest, service-worker)

## Metrics

This template is developed with optimized performance and security in mind. The following benchmarks are
performed against the demo installation on production. It uses an inexpensive virtual server on the [Hetzner Cloud](https://www.hetzner.com/de/cloud) behind a [Traefik](https://traefik.io/traefik/) setup.

### Lighthouse site performance

100% in all categories.

![Lighthouse](docs/lighthouse.png)

### Security headers

[![Security headers](docs/security-headers.png)](https://securityheaders.com/?q=templatus_view_component_reflex.ledermann.dev&followRedirects=on)

What's the red _Permissions-Policy_ badge? This seems to be fixed with one of the next Rails update:
https://github.com/rails/rails/pull/41994

### Mozilla Observatory

[![Mozilla Observatory](docs/mozilla-observatory.png)](https://observatory.mozilla.org/analyze/templatus_view_component_reflex.ledermann.dev)

### WebPageTest

[![WebPageTest](docs/web-page-test.png)](https://www.webpagetest.org/result/220530_BiDcQQ_83b754931114d99469b521e72731eb4d/)

### GTmetrix

[![GTmetrix](docs/GTmetrix.png)](https://gtmetrix.com/reports/templatus_view_component_reflex.ledermann.dev/rSqolxsw/)

### Check-your-website

[![Check-your-website](docs/check-your-website.png)](https://check-your-website.server-daten.de/?q=templatus_view_component_reflex.ledermann.dev)

### JavaScript size

142 KB of compiled JavaScript (minified, uncompressed). The largest parts are:

- Turbo with ActionCable (72 KB)
- Stimulus (32 KB)
- Honeybadger (25 KB)

```
$ RAILS_ENV=production bin/rails assets:precompile
yarn install v1.22.19
[1/5] 🔍  Resolving packages...
success Already up-to-date.
✨  Done in 0.07s.
Building with Vite ⚡️
vite v3.1.8 building for production...
transforming...
✓ 45 modules transformed.
rendering chunks...
../../public/vite/assets/logo.cfef1aba.svg          0.48 KiB
../../public/vite/manifest-assets.json              0.10 KiB
../../public/vite/manifest.json                     0.78 KiB
../../public/vite/assets/application.ccca36ce.js    2.91 KiB / gzip: 1.19 KiB
../../public/vite/assets/application.ccca36ce.js.map 7.10 KiB
../../public/vite/assets/index.78c8fc7f.js          8.83 KiB / gzip: 2.82 KiB
../../public/vite/assets/index.78c8fc7f.js.map      29.44 KiB
../../public/vite/assets/application.9f0093dd.css   20.74 KiB / gzip: 4.60 KiB
../../public/vite/assets/vendor.917f000c.js         145.74 KiB / gzip: 40.22 KiB
../../public/vite/assets/vendor.917f000c.js.map     484.65 KiB
Build with Vite complete: /Users/ledermann/Projects/templatus_view_component_reflex/public/vite
```

### Network transfer

Small footprint: The demo application transfers only **51 KB** of data on the first visit.

![Network](docs/network.png)

### Docker build time

With multi-stage building and using [DockerRailsBase](https://github.com/ledermann/docker-rails-base) the build of the Docker image takes very little time. Currently, the build job requires about 1,5 minutes on GitHub Actions (see https://github.com/templatus/templatus_view_component_reflex/actions)

### Docker image size

The Docker image is based on Alpine Linux and is optimized for minimal size (currently **117 MB** uncompressed disk size). It includes just the bare minimum - no build tools like Node.js, no JS sources (just the compiled assets), no tests.

```
$ container-diff analyze ghcr.io/templatus/templatus_view_component_reflex -n

-----Size-----

Analysis for ghcr.io/templatus/templatus_view_component_reflex:
IMAGE                                      DIGEST       SIZE
ghcr.io/templatus/templatus_view_component_reflex        sha256:... 116.7M
```

## Getting started

### Install for development

1. Clone the repo locally:

```bash
git clone git@github.com:templatus/templatus_view_component_reflex.git
cd templatus_view_component_reflex
```

2. Install PostgreSQL, Redis, and puma-dev (if not already present). On a Mac with HomeBrew, run this to install from the `Brewfile`:

```bash
brew bundle
```

3. Install and set up [puma-dev](https://github.com/puma/puma-dev) to use HTTPS for development. Do this on macOS:

```bash
sudo puma-dev -setup
puma-dev -install
puma-dev link

# Use Vite via puma-dev proxy
# Adopted from https://github.com/puma/puma-dev#webpack-dev-server
echo 3036 > ~/.puma-dev/vite.templatus_view_component_reflex
```

4. Setup the application to install gems and NPM packages and create the database:

```bash
bin/setup
```

5. Start the application locally:

```bash
bin/dev
```

Then open https://templatus_view_component_reflex.test in your browser.

### Preview components in LookBook

```bash
bin/dev
```

Then open https://templatus_view_component_reflex.test/lookbook/ in your browser.

### Running linters

RuboCop:

```
bin/rubocop
```

ESLint:

```
bin/yarn lint
```

### Running tests locally

Ruby tests:

```
bin/rspec
open coverage/index.html
```

JavaScript unit tests:

```
bin/yarn test
```

E2E tests with Cypress:

```
bin/cypress open
```

This opens Cypress and starts Rails in `development` environment, but with `CYPRESS=true`, so the `test` database is used. This allows code editing without class reloading and recompiling assets.

To run Cypress in headless mode:

```
bin/cypress run
```

### Test deployment locally

```
docker network create public
docker-compose up
```
