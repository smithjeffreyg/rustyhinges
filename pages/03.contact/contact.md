---
title: Contact
media_order: trees-bg.jpg
subheading: 'Have questions? Me too!'
header_image: trees-bg.jpg
menu: Contact
form:
    name: contact-form
    message_color: danger
    fields:
        -
            name: name
            label: THEME_CLEAN_BLOG.CONTACT.NAME
            placeholder: THEME_CLEAN_BLOG.CONTACT.NAME
            type: text
            validate:
                required: true
            classes: form-control
        -
            name: email
            label: THEME_CLEAN_BLOG.CONTACT.EMAIL
            placeholder: THEME_CLEAN_BLOG.CONTACT.EMAIL
            type: email
            validate:
                required: true
            classes: form-control
        -
            name: phone
            label: THEME_CLEAN_BLOG.CONTACT.PHONE
            placeholder: THEME_CLEAN_BLOG.CONTACT.PHONE
            type: text
            classes: form-control
        -
            name: message
            label: THEME_CLEAN_BLOG.CONTACT.MESSAGE
            placeholder: THEME_CLEAN_BLOG.CONTACT.MESSAGE
            type: textarea
            rows: 5
            validate:
                required: true
            classes: form-control
    buttons:
        -
            type: submit
            value: THEME_CLEAN_BLOG.CONTACT.SEND
            classes: 'btn btn-default'
    process:
        -
            email:
                from: '{{ config.plugins.email.from }}'
                to:
                    - '{{ config.plugins.email.from }}'
                subject: '[Contact] {{ form.value.name|e }}'
                body: '{% include ''forms/data.html.twig'' %}'
        -
            save:
                fileprefix: contact-
                dateformat: Ymd-His-u
                extension: txt
                body: '{% include ''forms/data.txt.twig'' %}'
        -
            display: thank-you
        -
            reset: true
---

Want to chat? Fill out the form below and I will try to get back to you soon!
