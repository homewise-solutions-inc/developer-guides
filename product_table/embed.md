# Embed Homewise Product Table
Thank you for partnering with Homewise!

This guide covers the steps to embed Homewise product table into your website.

## Installation

### Step 1
Complete [partner configuration](../partner/configuration.md).

### Step 2
Paste following line right after the `homewise` object. This loads the widget embed script.

```html
<script src="https://widgets.thinkhomewise.com/lib/com-product-table/1.5/embed.js"></script>
```

#### Example
```html
<script>
  var homewise = {
    partner: {
      type: "p",
      code: "foo",
      segment: "bar"
    }
  };
</script>
<script src="https://widgets.thinkhomewise.com/lib/com-product-table/1.5/embed.js"></script>
```

#### Versions
Homewise will release versions time to time introducing new features and bug fixes. We recommend that you use the latest 
version of embed script by changing the version number (e.g `/1.5/embed.js`). Following table shows available versions.

|            Version            | Notes                                                                    |
|:-----------------------------:|--------------------------------------------------------------------------|
|              1.5              | Customizable search input values.                                        |
| [1.4](./archive/embed_1.4.md) | Available rental rate options.                                           |
| [1.3](./archive/embed_1.3.md) | Optimized. Links take `segment` into account. CTA label is customizable. |
| [1.0](./archive/embed_1.0.md) | First version with all launch features.                                  |


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
      cta: <string>,
      rental: <string>,
      mortgageType: <string>,
      rateType: <string>,
      price: <number>,
      downPayment: <number>,
      balance: <number>
    }
  };
</script>
```

#### Reference
| Property       | Required | Accepted Values                                                        | Default                        | Version |
|----------------|:--------:|------------------------------------------------------------------------|--------------------------------|---------|
| `bg`           |    N     | `^#(?:[0-9a-fA-F]{3}){1,2}$`                                           | `#ffffff`                      | 1.0+    |
| `primaryColor` |    N     | `^#(?:[0-9a-fA-F]{3}){1,2}$`                                           | `#147bc9`                      | 1.0+    |
| `font`         |    N     | `true`,`false`                                                         | `true`                         | 1.0+    |
| `intro`        |    N     | `true`,`false`                                                         | `true`                         | 1.0+    |
| `province`     |    N     | `AB`, `BC`, `MB`, `NB`, `NL`, `NS`, `ON`, `PE`, `SK`, `NT`, `NU`, `YT` | `ON`                           | 1.0+    |
| `cta`          |    N     | `<STRING>`                                                             | `Get This Mortgage`            | 1.3+    |
| `link`         |    N     | `<URI>`                                                                | `https://my.thinkhomewise.com` | 1.3+    |
| `rental`       |    N     | `no`, `mixed`, `filtered`                                              | `no`                           | 1.4+    |
| `mortgageType` |    N     | `purchase`, `refinance`, `switch`                                      | `purchase`                     | 1.5+    |
| `rateType`     |    N     | `fixed`, `variable`                                                    | `fixed`                        | 1.5+    |
| `price`        |    N     | `80000` - `100000000`                                                  | `650000`,`1000000`             | 1.5+    |
| `downPayment`  |    N     | `0` - `100000000`                                                      | `90000`, `200000`              | 1.5+    |
| `balance`      |    N     | `0` - `100000000`                                                      | `130000`                       | 1.5+    |

##### Notes
* `bg` - Set default background color. Consider accessibility concerns when selecting the colour.
* `primaryColor` - Set default primary color. This sets colors for buttons and borders. Consider accessibility concerns when 
  selecting the colour.
* `font` - Toggle standard font load. `false` will allow you to apply the font used your website's CSS.
* `intro` - Toggle leading headline and introduction copy. Customization is not allowed, but by toggling you can position
  your own copy before the app embed container and make it seamless.
* `province` - Set default province selection.
* `cta` - Set default CTA label. Provided value is converted to uppercase automatically.
* `link` - Set a custom click through URL. Assuming Homewise online application is embedded in this custom URL:
  * `hw_product` URL variable must be captured and send back to embedded app as `hw_product` URL variable.
  * `hw_state` URL variable must be captured and send back to embedded app as `state` URL variable.
  * `hw_segment` URL variable must be captured and send back to embedded app as part of the path before `/embed` bit.
    * _e.g. **with** `hw_segment` - `https://my.thinkhomewise.com/<partner_type>/<partner_code>/<hw_segment>/embed?hw_product=<hw_product>&state=<hw_state>` 
     (`https://my.thinkhomewise.com/p/abc123/xyz789/embed?hw_product=prod456&state=aBc753dEf`)_
    * _e.g. **without** `hw_segment` - `https://my.thinkhomewise.com/<partner_type>/<partner_code>/embed?hw_product=<hw_product>&state=<hw_state>`.
     (`https://my.thinkhomewise.com/p/abc123/embed?hw_product=prod456&state=aBc753dEf`)_
* `rental` - Show available rental rates.
  * `no` - Do not show rental rates. Default value.
  * `mixed` - Include rental rates in the results. Shows a user controller to toggle between normal rates and mixed results.
  * `filtered` - Show only rental rates.
* `price` - Set price amount. Value is shared with rental and non-rental views. Please find a value with more results.
  If not set, 2 indicated default values are used (for `rental:no|mixed` and `rental:filtered` respectively).
* `downPayment` - Set down payment amount for purchase. Value is shared with rental and non-rental views. Please find a
  value with more results. If not set, 2 indicated default values are used (for `rental:no|mixed` and `rental:filtered` 
  respectively).
* `balance` - Set balance amount for refinance/switch. options on both rental and non-rental views. Please find a value 
  with more results.

#### Example
```html
<script>
  var homewise = {
    partner: {
      type: "p",
      code: "foo",
      segment: "bar"
    },
    productTable: {
      bg: "#fff7ed",
      primaryColor: "#ff824d",
      font: false,
      intro: false,
      province: "BC",
      link: "https://domain.com/page?foo=123&bar=456",
      cta: "Learn More",
      rental: "mixed",
      mortgageType: "purchase",
      rateType: "fixed",
      price: 650000,
      downPayment: 90000,
      balance: 130000
    }
  };
</script>
<script src="https://widgets.thinkhomewise.com/lib/com-product-table/1.5/embed.js"></script>
```

## Support
Contact Homewise Solutions Inc. at *hello[at]thinkhomewise.com* for support. Feel free to report any bugs you find via 
email or on GitHub.

**© Homewise Solutions Inc. All rights reserved.**

[Privacy Policy](https://thinkhomewise.com/page/privacy/) | [Terms of Agreement](https://thinkhomewise.com/page/term/).







