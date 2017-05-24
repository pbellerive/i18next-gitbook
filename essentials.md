<!-- toc -->
# Essentials

{% method %}
## Accessing keys

keys

```json
{
    "key": "value of key",
    "look": {
        "deep": "value of look deep"
    }
}
```

{% sample lang="js" %}
sample

```js
i18next.t('key');
// -> "value of key"

i18next.t('look.deep');
// -> "value of look deep"

```

{% endmethod %}


{% method %}
## Accessing keys in different namespaces

Namespaces are a feature in i18next internationalization framework which allows you to separate translations that get loaded into multiple files.

init

```js
i18next.init({
  ns: ['common', 'moduleA'],
  defaultNS: 'moduleA'
});
```

moduleA.json

```json
{
    "name": "Module A"
}
```

common.json

```json
{
    "button": {
        "save": "save"
    }
}
```

{% sample lang="js" %}
sample

```js
i18next.t('name');
// -> "Module A"

i18next.t('common:button.save');
// -> "save"

```
{% endmethod %}


{% method %}
## Multiple fallback keys

Calling the t function with an array of keys enables you to translate dynamic keys providing a non specific fallback value.

As a sample think of an error code you get and you like to show a specific warning in some cases:

keys

```json
{
  "error": "Something went wrong.",
  "error.404": "The page was not found."
}
```

{% sample lang="js" %}
sample

```js
// const error = '404';
i18next.t([`error.${error}`, 'error']); // -> "The page was not found"

// const error = '502';
i18next.t([`error.${error}`, 'error']); // -> "Something went wrong"
```

{% endmethod %}


