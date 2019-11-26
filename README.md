# Hello San

No ideas 🤖 But i have ideas 😅

A Simple and Responsive Ghost Blog theme.

- Ghost v3 - <https://ghost.org/3/>
- Ghost theme with Membership Feature - <https://ghost.org/members/>
- Ghost theme for My Personal Blog - Automatically deploy to Ghost Admin Dasboard

> Experimenting the Ghost Membership Feature Here

## Development 🛠

- Download or install via git on your Ghost theme Directory `/content/themes/`

```bash
git clone https://github.com/mskian/hell-san.git
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

- Enable Static Home page and Blog Post page - Login to your Ghost Admin Dashboard and Upload this routes file on Lab Section
- Next Open post Editor and Goto Pages - Create a New Page with permalink `home`
- Add this Below Registration Code on HTML Block

```html
<div class="card-content content user-form login">

<ul class="has-text-weight-bold">
<li>Enter your Email - Accecpt the Terms and policy by Checking the checkbox</li>
<li>After Successful Signup, you will Recieve the Account Activation Link on your Email</li>
</ul>
 <br>
 <form id="sigupData" data-members-form="signup">
 <div class="field">
<label class="label has-text-centered has-text-grey-dark">Your email address*</label>
 <div class="control">
 <input class="input is-info column is-half input-box" type="text" data-members-email name="email" id="email" placeholder="Email address">
 </div>
 </div>

<div class="subtitle has-text-centered">
<label class="checkbox">
<input id="check" name="check" type="checkbox" style="display:inline;" onchange="RegisterAgreement()">
</label>
<p class="has-text-danger has-text-weight-bold" style="font-size:14px; margin:2px; vertical-align:middle; display:inline;">
Yes, I Accept this website Privacy and Cookie Policy to Continue My Registration
</p>
</div>

<div class="control">
<button id="pushdata" type="submit" class="button is-success sign-button" disabled>📝 Register</button>
</div>
<br>
<div class="has-text-centered" id="registernotice"></div>
</form>
<br>
<p class="has-text-weight-bold has-text-centered"><small>Already Having an Account &rarr; <a href="http://localhost:2368/login/">Log in</a></small></p>

</div>
```

`routes.yaml`

```yaml
routes:
  /:
    data: page.home
    template: home
  /login/:
    template: login

collections:
  /blog/:
    permalink: /blog/{slug}/
    template: index
    filter: slug:-home

taxonomies:
  tag: /tag/{slug}/
  author: /author/{slug}/
```

## LICENSE 📜

MIT
