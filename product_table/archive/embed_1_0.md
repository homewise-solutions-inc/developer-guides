# Embed Homewise Product Table
Thank you for partnering with Homewise!

This guide covers the steps to embed Homewise product table into your website.

## Installation

### Step 1
Complete [partner configuration](../../partner/configuration.md).

### Step 2
Paste following line right after the `homewise` object. This loads the widget embed script.

```html
<script src="https://widgets.thinkhomewise.com/lib/com-product-table/1.0/embed.js"></script>
```

#### Example
```html
<script>
  var homewise = {
    partner: {
      type: "p",
      code: "abc123"
    }
  };
</script>
<script src="https://widgets.thinkhomewise.com/lib/com-product-table/1.0/embed.js"></script>
```

#### Versions
Homewise will release versions time to time introducing new features and bug fixes. We recommend that you use the latest 
version of embed script by changing the version number (e.g `/1.0/embed.js`). Following table shows available versions.

| Version | Notes                                   |
|:-------:|-----------------------------------------|
|   1.0   | First version with all launch features. |


### Step 3
Paste following code where you want the Homewise product table to appear.
```html
<div class="homewise_product_table"></div>
```

### Step 4 - Optional
Optionally, customize the product table by adding `productTable` configuration object to the `homewise` default object.
> :warning: Please refer to browser's console for errors.

```html
<script>
  var homewise = {
    partner: { ... },
    productTable: {
      bg: <string>,
      primaryColor: <string>,
      font: <boolean>,
      intro: <boolean>,
      province: <string>,
      link: <string>,
      cta: <string>
    }
  };
</script>
```

| Property       | Required | Accepted Values                                                  | Default                        | Notes                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|----------------|:--------:|------------------------------------------------------------------|--------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `bg`           |    N     | *Any hexadecimal color code.*                                    | `#ffffff`                      | Set default background color. Consider accessibility concerns when selecting the the colour.                                                                                                                                                                                                                                                                                                                                                  |
| `primaryColor` |    N     | *Any hexadecimal color code.*                                    | `#147bc9`                      | Set default primary color. This sets colors for buttons and borders. Consider accessibility concerns when selecting the the colour.                                                                                                                                                                                                                                                                                                           |
| `font`         |    N     | `true`,`false`                                                   | `true`                         | Toggle standard font load. `false` will allow you to apply the font used your website's CSS.                                                                                                                                                                                                                                                                                                                                                  |
| `intro`        |    N     | `true`,`false`                                                   | `true`                         | Toggle leading headline and introduction copy.                                                                                                                                                                                                                                                                                                                                                                                                |
| `province`     |    N     | `AB`,`BC`,`MB`,`NB`,`NL`,`NS`,<br/>`ON`,`PE`,`SK`,`NT`,`NU`,`YT` | `ON`                           | Set default province selection.                                                                                                                                                                                                                                                                                                                                                                                                               |
| `link`         |    N     | *Any URL.*                                                       | `https://my.thinkhomewise.com` | Set click through URL. Assuming Homewise online application is embedded in this page: <br/>- Query string variable `hw_product` should be captured and send back to embedded app as `hw_product`. <br/>- Query string variable `hw_state` should be captured and send back to embedded app as `state`. <br/><br/>e.g. `https://my.thinkhomewise.com/p/abc123/<hw_product_value>/embed?hw_product=<hw_product_value>&state=<hw_state_value>`   |
| `cta`          |    N     | *Any string*                                                     | `Get This Mortgage`            | Set default CTA label. Provided value is converted to uppercase automatically.                                                                                                                                                                                                                                                                                                                                                                |


#### Example
```html
<script>
  var homewise = {
    partner: {
      type: "p",
      code: "abc123"
    },
    productTable: {
      bg: "#fff7ed",
      primaryColor: "#ff824d",
      font: false,
      intro: false,
      province: "BC",
      link: "https://domain.com/page?foo=123&bar=456",
      cta: "Learn More"
    }
  };
</script>
<script src="https://widgets.thinkhomewise.com/lib/com-product-table/1.0/embed.js"></script>
```

## Support
Contact Homewise Solutions Inc. at *hello[at]thinkhomewise.com* for support. Feel free to report any bugs you find via 
email or on GitHub.

**© Homewise Solutions Inc. All rights reserved.**

[Privacy Policy](https://thinkhomewise.com/page/privacy/) | [Terms of Agreement](https://thinkhomewise.com/page/term/).







