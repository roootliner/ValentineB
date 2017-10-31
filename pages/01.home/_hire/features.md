---
title: KONTAKT
form:
    name: HIRE
    fields:
        -
            name: name
            label: Name
            placeholder: Name
            autocomplete: 'on'
            type: text
            validate:
                required: true
        -
            name: email
            label: Email
            placeholder: 'email address'
            type: email
            validate:
                required: true
        -
            name: message
            label: Message
            placeholder: Message
            type: textarea
            validate:
                required: true
        -
            name: g-recaptcha-response
            label: Captcha
            type: captcha
            recaptcha_site_key: ENTER_YOUR_CAPTCHA_SITE_KEY
            recaptcha_not_validated: 'Captcha not valid!'
            validate:
                required: true
    buttons:
        -
            type: submit
            value: Submit
    process:
        -
            captcha:
                recaptcha_secret: ENTER_YOUR_CAPTCHA_SECRET_KEY
        -
            email:
                subject: '[Site Contact Form] {{ form.value.name|e }}'
                body: '{% include ''forms/data.html.twig'' %}'
        -
            save:
                fileprefix: hire-
                dateformat: Ymd-His-u
                extension: txt
                body: '{% include ''forms/data.txt.twig'' %}'
        -
            message: 'Thank you for getting in touch!'
        -
            display: thankyou
---

## Contact
