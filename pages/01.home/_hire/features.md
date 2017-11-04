---
title: KONTAKT
template: modular/form
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
            placeholder: 'Email adress'
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
            recaptcha_site_key: 6Lff0jYUAAAAAGAWe33NbyusGGeBRcFZ9WtP8MWm
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
                recaptcha_secret: 6Lff0jYUAAAAAGXxoxhcDWJcbcjmSEdnhBrPZL6m
        -
            email:
                subject: 'Nachricht von {{ form.value.name|e }}'
                body: '{% include ''forms/data.html.twig'' %}'
        -
            save:
                fileprefix: hire-
                dateformat: Ymd-His-u
                extension: txt
                body: '{% include ''forms/data.txt.twig'' %}'
        -
            message: 'Danke für die Nachricht'
        -
            display: thankyou
---

## Kontakt
