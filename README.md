# Hello San ✌

No ideas 🤖 But i have ideas 😅

> Experimenting ⚗ the Ghost Membership Feature, Dynamic URLs & Dynamic Routing

A Simple and Responsive Ghost Blog theme for Email Newsletters 📮

- Ghost v3 - <https://ghost.org/3/>
- Ghost theme with Membership Feature - <https://ghost.org/members/>
- Build Membership Feature - <https://ghost.org/docs/members/introduction/>
- Ghost Dynamic URLs & Dynamic Routing - <https://ghost.org/docs/api/v3/handlebars-themes/routing/>
- Native Email Newsletters - <https://ghost.org/blog/native-email/>

📦 **Goal**: Build Free Memebership Site + Email Newsletters on Ghost with Static Home page

- [x] Static Home Page
- [x] Registration Form on Home page
- [x] Custom registration Page  - `https://example.com/register/`
- [x] Custom Login Page - `https://example.com/login/`
- [x] Form Validation
- [x] User Dasboard
- [x] Newsletter Page - `https://example.com/newsletter/`
- [x] Native Email NewsLetters
- ~~Paid Membership Feature~~ - Build Free Memebership Site with Newsletter Feature

## Development 🛠

- Download or install via git on your Ghost theme Directory `/content/themes/`

```bash
git clone https://github.com/mskian/hello-san.git
```

- Install Modules via `yarn`

```bash
yarn
```

- Workflow ⚙

```bash
## Development (Run build & watch for changes)
yarn dev
```

```bash
## Build
yarn buld
```

```bash
## Gscan
yarn test
```

```bash
## Bundle the theme to zip for Production use
yarn zip
```

- Enable Static Home page and Blog Post page
- Login to your Ghost Admin Dashboard and Upload this routes file on Lab Section

`routes.yaml`

```yaml
routes:
  /:
    data: page.home
    template: home
  /login/:
    template: login
  /register/:
    template: register

collections:
  /newsletter/:
    permalink: /newsletter/{slug}/
    template: index
    filter: slug:-home

taxonomies:
  tag: /tag/{slug}/
  author: /author/{slug}/
```

- Open post Editor and Goto Pages - Create a New Page with permalink `home`
- Add some text Contents
- Next Add this Below Registration Code in the HTML Block

```html
<div class="card-content content user-form login">
<ul class="has-text-weight-medium">
<li>Enter your Email - Accecpt the Terms and policy by Checking the checkbox</li>
<li>After Successful Signup, you will Recieve the Account Activation Link on your Email</li>
</ul>
<br>
<form id="sigupData" data-members-form="signup">
<div class="field">
<label class="label has-text-centered has-text-weight-medium">Your email address*</label>
<div class="control">
<input class="input is-info column is-half input-box" type="text" data-members-email name="email" id="email" placeholder="Email address">
</div>
</div>
<input data-members-label type="hidden" value="Home Page" />
<div class="subtitle has-text-centered">
<label class="checkbox">
<input id="check" name="check" type="checkbox" style="display:inline;" onchange="RegisterAgreement()">
</label>
<p class="has-text-danger has-text-weight-medium" style="font-size:14px; margin:2px; vertical-align:middle; display:inline;">
Yes, I Accept this website Privacy and Cookie Policy to Continue My Registration
</p>
</div>
<div class="control">
<button id="pushdata" type="submit" class="button is-success sign-button" disabled>📝 Register</button>
</div>
<br>
<div class="has-text-centered" id="registernotice"></div>
<br>
<p class="has-text-centered" data-members-error><!-- error message will appear here --></p>
</form>
<br>
<p class="has-text-weight-bold has-text-centered"><small>Already Having an Account &rarr; <a href="http://localhost:2368/login/">Log in</a></small></p>
</div>
```

## LICENSE 📜

MIT
