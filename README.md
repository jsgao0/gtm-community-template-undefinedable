# Variable template

The `gtm-community-template-undefinedable` is a variable template of Google Tag Manager. It returns `undefined` if a property is absent in the latest layer in dataLayer.

## Why
Imagine that if a variable in pushed layer:

- first time: `dataLayer.push({ event: 'create_order', order_amount: 300, delivery_fee: 80 })`
- second time: `dataLayer.push({ event: 'create_order', order_amount: 300 })`

It returns `80` for variable `delivery_fee` if it's from built-in Data Layer Variable. But for me, it should be `undefined` instead of `80` implicitly as it's absent in the pushed object.