# FORME. Assignment #4: Forms and Validation

**Student:** Mumina Mukazhan
**Group:** SE-2530
**Live site:** https://muminamukazhan.github.io/webtech4/
**Repository:** https://github.com/muminamukazhan/webtech4

## Description

FORME is a small multi-page website for Assignment #4. It shows how to build user-friendly forms with HTML, style them with Bootstrap form components and validate them with HTML5 built-in validation and Bootstrap validation styles.

A navbar on every page links to all parts of the assignment, so each task is on its own page. The design is a clean black and white style with soft gray cards, rounded corners and black pill buttons.

The project uses no custom JavaScript. All validation is done with HTML5 attributes and CSS.

## Pages and tasks

| Page | Task | What it contains |
|------|------|------------------|
| `index.html` | Home | Short intro and cards that link to every task |
| `task0.html` | Task 0. Simple Contact Form | Name (text), Email (email), Message (textarea) and a submit button. Every field has a `<label>` connected with `for` and `id` |
| `task1.html` | Task 1. Form with HTML5 Validation | `required`, `type="email"`, `type="tel"` with `pattern`, `type="number"` with `min` and `max`, `minlength`, `maxlength` and a required checkbox. The browser enforces the rules |
| `task2.html` | Task 2. Bootstrap Form Styling | The contact form rebuilt with `form-label`, `form-control`, `form-select` and `form-check`. Fields are arranged with the Bootstrap grid (`row`, `col-md-6`). Placeholders and `form-text` helper text are included |
| `task3.html` | Task 3. Bootstrap Validation Styles | `is-valid` and `is-invalid` classes in a static example, plus a live form with `valid-feedback` ("Looks good!") and `invalid-feedback` ("Email is required", etc.) under each input |
| `task4.html` | Task 4. Registration Form | First name, last name, email, password and confirm password, gender (radio buttons), hobbies (checkboxes), country (select), Submit and Reset buttons. Responsive Bootstrap grid, HTML5 validation (password minimum 8 characters with a letter and a digit) and Bootstrap feedback messages |
| `success.html` | Success page | Opens after a valid form is submitted in Task 1, Task 3 or Task 4 |

## Project structure

```
project/
├── index.html
├── task0.html
├── task1.html
├── task2.html
├── task3.html
├── task4.html
├── success.html
├── css/
│   └── style.css
└── README.md
```

## Technologies

- HTML5
- CSS3 (custom styles in `css/style.css`)
- Bootstrap 5.3.3 (loaded from the jsDelivr CDN)
- Inter font (Google Fonts)
- No custom JavaScript. The Bootstrap bundle is used only for the mobile navbar menu.

## How to run locally

1. Download or clone the repository.
2. Open `index.html` in a browser.
3. Use the navbar to move between the tasks.

No installation or build step is needed. Bootstrap and the font are loaded from a CDN, so an internet connection is required.

## How to publish with GitHub Pages

1. Create a new repository on GitHub and upload all project files. Keep `index.html` in the root of the repository.
2. Open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select branch `main` and folder `/ (root)`, then press **Save**.
5. After about a minute the site is available at `https://USERNAME.github.io/REPOSITORY/`.

Netlify also works: drag the project folder to https://app.netlify.com/drop.

## How validation works

- **HTML5 validation.** Rules are written as attributes on the inputs: `required`, `type`, `minlength`, `maxlength`, `pattern`, `min`, `max`. The browser blocks the form and shows a message when data is wrong.
- **Bootstrap feedback in Task 3 and Task 4.** The form has the class `live-validation`. CSS rules in `css/style.css` use the `:user-valid` and `:user-invalid` pseudo-classes. After the user types in a field, the border turns green or red and the matching `valid-feedback` or `invalid-feedback` message appears under the input.
- **`is-valid` and `is-invalid` classes.** Task 3 shows both Bootstrap classes in the "Static examples" block.
- **Radio group.** `required` on the gender radio buttons forces the user to choose one option.
- **Success page.** When all fields are valid, the form opens `success.html`. The project has no server, so this page replaces the server response. Password fields have no `name` attribute, so passwords are never sent in the address bar.
- **Limitation.** Comparing Password and Confirm password needs JavaScript, so this version only checks that both fields follow the password rule.
- Live feedback works in modern browsers (Safari 16.5+, Chrome 119+, Firefox 88+).

## Testing

| Task | What to try | Expected result |
|------|-------------|-----------------|
| 1 | Submit an empty form | The browser shows "fill out this field" |
| 1 | Type `abc` in Email | The browser says the email format is wrong |
| 1 | Type a phone number without `+7` | The browser shows the format hint |
| 3 | Type an invalid email and leave the field | Red field and an error message under it |
| 3 | Enter a valid name | Green field and "Looks good!" |
| 4 | Enter a password shorter than 8 characters | Red field with the password rule |
| 4 | Skip Gender and Country and submit | The browser asks to select an option |
| 4 | Fill everything correctly and press Register | The success page opens |
| 4 | Press Reset | All fields are cleared |

## Resources

- [Bootstrap 5.3 Forms](https://getbootstrap.com/docs/5.3/forms/overview/)
- [Bootstrap 5.3 Validation](https://getbootstrap.com/docs/5.3/forms/validation/)
- [MDN: Web forms](https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Forms)
- [W3Schools: HTML form attributes](https://www.w3schools.com/html/html_form_attributes.asp)
