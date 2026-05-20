# Change Log

We are updating the **Bootstrap 5 Quick Snippet** extension in regular basis to give you the best performance while developing projects.

## [0.6.0] - 2026-05-20

Massive expansion: full pages, large adaptive blocks, admin kit and PHP/RedBeanPHP backend snippets.

### Added — full pages (`bs5-pages-*`)

- `login`, `register`, `dashboard`, `profile`, `landing`, `pricing`, `contact`, `404`, `500`, `maintenance`, `coming-soon`.

### Added — landing-building blocks (`bs5-blocks-*`, 27 snippets)

- Heroes: `hero-centered`, `hero-split`, `hero-image-bg`, `hero-gradient`.
- Features: `features-3col`, `features-alternating`, `features-icons-grid`, `feature-tabs`.
- Pricing: `pricing-3-tier`, `pricing-toggle`.
- Social proof: `testimonials`, `testimonial-single`, `logo-cloud`, `stats`.
- Community: `team`, `faq`, `timeline`, `gallery-grid`.
- Conversion: `cta-simple`, `cta-newsletter`, `cta-card`, `newsletter-inline`, `contact-form`.
- Layout: `header-cover`, `footer-simple`, `footer-columns`, `footer-dark`.

### Added — admin kit (`bs5-admin-*`)

- `sidebar`, `sidebar-dark`, `topbar`, full `layout` (offcanvas on mobile, static on md+).
- `stats-cards`, `data-table`, `activity-feed`, `chart-placeholder`, `inbox`, `kanban`, `profile-card`, `form-card`.

### Added — auth (`bs5-auth-*`)

- `login`, `login-split`, `login-social`, `register`, `register-split`, `forgot-password`, `reset-password`, `otp`, `lock-screen`.

### Added — e-commerce (`bs5-shop-*`)

- `product-card`, `product-grid`, `product-detail`, `cart-table`, `checkout-form`, `category-sidebar`.

### Added — carousels (`bs5-carousel-*`)

- `hero` (full-bleed slides with CTA), `multi-item`, `testimonial`, `full-width` (responsive 21:9 ratio).

### Added — Bootstrap 5 flex layout (`bs5-stack-*`)

- `horizontal` (`hstack`), `vertical` (`vstack`), `media-object` — flex-based replacement for the removed BS4 media object.

### Added — full PHP/RedBeanPHP backend (`php-*`, only in `.php` files)

- `php-app-bootstrap` — session, RedBean setup, CSRF init, helpers autoload.
- `php-helpers-all` — `e()`, `csrf_token()`, `csrf_field()`, `csrf_check()`, `flash()`, `render_flashes()`, `redirect()`, `current_user()`, `require_auth()`, `require_admin()`, `old()`.
- `php-helpers-sanitize`, `php-helpers-upload` — safe input + file upload.
- `php-auth-login`, `php-auth-register`, `php-auth-logout`, `php-auth-forgot`, `php-auth-reset`, `php-auth-middleware` — entire authentication system wired to BS5 forms.
- `php-admin-layout` — reusable admin layout (sidebar + topbar + content slot).
- `php-admin-dashboard`, `php-admin-users-list`, `php-admin-user-edit`, `php-admin-user-delete`, `php-admin-crud-list` — admin pages with search, pagination, CSRF-protected delete.
- `php-redbean-setup`, `php-redbean-crud-create/read/update/delete`, `php-redbean-pagination`, `php-redbean-search`, `php-redbean-transaction`, `php-redbean-relation`.
- `php-components-flash`, `php-components-pagination`, `php-components-form-errors`, `php-components-form-handler`.

### Added — starter

- `bs5-starter-full` — complete HTML5 boilerplate with navbar, main slot, footer and OG meta tags.

### Improved

- `bs5-$` — added Bootstrap Icons CDN, `data-bs-theme` choice includes `auto`, OG description, language picker.
- All new templates are responsive (`col-sm/md/lg/xl`, `flex-column flex-sm-row`, `d-none d-md-block`).

### Removed (obsolete in Bootstrap 5)

- `bs5-media-*` (Media object — replaced by `bs5-stack-*` using flex utilities).
- `bs5-jumbotron-*` (removed from BS5 — replaced by `bs5-blocks-hero-*`).
- `bs5-progress-ie9` (IE9 artifact).

### Tooling

- `scripts/generate-main-and-css-snippets.js` now also emits `snippets/php.code-snippets`.
- `package.json` registers `php.code-snippets` for the `php` language scope only.

## [0.5.0] - 2026-04-10

- feat(scripts): Added repository-local snippet generator for `snippets.code-snippets` and `css.code-snippets` from `src/templates`.
- feat(scripts): Added snippet generation commands in `package.json`:
    - `generate:main-css-snippets`
    - `generate:icons-snippets`
    - `generate:snippets`
- feat(templates): Organized icon templates under `src/templates/icons` and added Bootstrap Icons CDN template.

## [0.4.4] - 2023-12-06

- fix(templates): Used Tab indent(4 spaces) and removed all possible spaces.

## [0.4.3] - 2023-11-27

- fix(templates): Updated Bootstrap CDN to `5.2.1` to `5.2.3`

## [0.4.1] - 2022-09-04

- docs: Readme table not aligned properly

## [0.4.0] - 2022-08-29

- feat(templates): Snippet suggestion & code improvements [@uguryuruk][https://github.com/uguryuruk]
- Updated templates to: Bootstrap 5.2.0

## [0.3.0] - 2022-06-01

- feat(templates): Snippet suggestion & code improvements [@uguryuruk][https://github.com/uguryuruk]
- Updated templates to: Bootstrap 5.2.0-beta1 & fontawesome-cdn

## [0.2.3] - 2022-05-29

- feat(docs): Contribution page along with html templates.

## [0.2.2] - 2022-01-06

- Fix: svelte snippets path in package.json [@dealeros](https://github.com/dealeros)

## [0.2.1] - 2021-12-11

- Fix: formatted [README.md](./README.md)

## [0.2.1] - 2021-12-11

- Added support for `.svelte` support.
- Added the following:
    - `bs5-navbar-offcanvas` snippet [(Docs)](https://getbootstrap.com/docs/5.2/components/navbar/#offcanvas)
    - `bs5-card-placeholder` snippet [(Docs)](https://getbootstrap.com/docs/5.2/components/placeholders/)
    - `bs5-form-floating` snippet [(Docs)](https://getbootstrap.com/docs/5.2/forms/floating-labels/#example)
    - Please tell us if you have any thing to add to the list.
    - #### Improves:
        - Added emoji to `openCyberDudeChannel`command

## [0.2.0] - 2021-07-22

- Rewrote the extension in Typescript
- #### Features:
    - Added Font-Awesome cdn links. Use `fa5-cdn` to write fontawesome CDN links, you can use CSS version or JS version. (Only one is necessary.)
    - Added snippets for `html-comment-block` to create quick html block comments.
    - Added snippets for `css-comment-block` to create quick css block comments.
    - **[ Experimental ]** - Added new command "`Open CyberDude YT Channel`" that will open cyberdude channel from inside `VSCode`. Just press `CTRL + P` and type `cyberdude` it will open the [`CyberDude YouTube Channel`](https://www.youtube.com/user/CyberDudeNetworks) and has the ability to visit [`cyberdude website`](https://cyberdudenetworks.com) aswell. This feature is experimental and can be removed in the future.

## [0.1.3] - 2021-07-18

- Made it compatible for VSCode `1.54.0` above.

## [0.1.2] - 2021-07-15

- Added 166 code snippets
- Fixed lot of bugs
