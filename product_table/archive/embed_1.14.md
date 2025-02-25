# Embed Homewise Product Table
Thank you for [partnering with Homewise](https://youtu.be/yz-ZVXk6R2k)! Remember, there are 
[multiple ways to share](https://www.youtube.com/watch?v=m2HKbYtsZl8) your personalized URL or widgets! 

This guide covers the steps to embed Homewise product table into your website.

## Installation

### Step 1
Complete [partner configuration](../partner/configuration.md).

### Step 2
Paste following line right after the `homewise` object. This loads the widget embed script.

```html
<script src="https://widgets.thinkhomewise.com/lib/com-product-table/1.14/embed.js"></script>
```

#### Example
```html
<script>
  var homewise = {
    partner: {
      type: "p",
      code: "partner_code_goes_here",
      segment: "optional_segment_goes_here"
    }
  };
</script>
<script src="https://widgets.thinkhomewise.com/lib/com-product-table/1.14/embed.js"></script>
```

#### Versions
Homewise will release versions with new features and bug fixes. We recommend that you use the latest 
version of embed script by changing the version number (e.g `/1.14/embed.js`). Following table shows available versions.

|             Version             | Notes                                                                    |
|:-------------------------------:|--------------------------------------------------------------------------|
|              1.14               | `linkParameters` and `linkFragments` added to enrich `link` param.       |
| [1.10](./archive/embed_1.10.md) | Updated `featureCount`. New click events and `style` options. Bug fixes. |
|  [1.9](./archive/embed_1.9.md)  | New `lenderName` filter added.                                           |
|  [1.8](./archive/embed_1.8.md)  | New `featureCount` & controller `hide` options. Visible product names.   |
|  [1.7](./archive/embed_1.7.md)  | Updated `rateType` options. New `creditScore` option.                    |
|  [1.6](./archive/embed_1.6.md)  | Multi widget configuration and more customizable search inputs.          |
|  [1.5](./archive/embed_1.5.md)  | Customizable search input values.                                        |
|  [1.4](./archive/embed_1.4.md)  | Available rental rate options.                                           |
|  [1.3](./archive/embed_1.3.md)  | Optimized. Links take `segment` into account. CTA label is customizable. |
|  [1.0](./archive/embed_1.0.md)  | First version with all launch features.                                  |

### Step 3
Use following target class naming format where `N` is the position (index) of the configuration in the configuration
array (see step 4 below). E.g. If 3 product tables were configured, then the targets will be `homewise_product_table_0`,
`homewise_product_table_1` and `homewise_product_table_2`.
```html
<div class="homewise_product_table_N"></div>
<!-- e.g. <div class="homewise_product_table_0"></div>, <div class="homewise_product_table_1"></div> -->
```

### Step 4
Customize the widget by adding `productTable` configuration object with a single or multiple banner customization
configurations to the `homewise` default object.
> [!WARNING]
> Please refer to browser's console for errors.

```html
<script>
  var homewise = {
    partner: { ... },
    productTable: [
      {
        bg: <string>,
        primaryColor: <string>,
        font: <boolean>,
        intro: <boolean>,
        province: <string>,
        cta: <string>,
        link: <string>,
        linkParameters: <object>,
        linkFragments: <object>,
        rental: <string>,
        mortgageType: <string>,
        rateType: <string>,
        price: <number>,
        downPayment: <number>,
        balance: <number>,
        term: <string>,
        lenderType: <string>,
        creditScore: <string>,
        featureCount: <number>,
        hide: [<string>],
        lenderName: [<string>],
        style: <string>                                      
      }
    ]
  };
</script>
```

#### Reference
| Property         | Required | Accepted Values                                                        | Default                        | Version |
|------------------|:--------:|------------------------------------------------------------------------|--------------------------------|---------|
| `bg`             |    N     | `^#(?:[0-9a-fA-F]{3}){1,2}$`                                           | `#ffffff`                      | 1.0+    |
| `primaryColor`   |    N     | `^#(?:[0-9a-fA-F]{3}){1,2}$`                                           | `#147bc9`                      | 1.0+    |
| `font`           |    N     | `true`,`false`                                                         | `true`                         | 1.0+    |
| `intro`          |    N     | `true`,`false`                                                         | `true`                         | 1.0+    |
| `province`       |    N     | `AB`, `BC`, `MB`, `NB`, `NL`, `NS`, `ON`, `PE`, `SK`, `NT`, `NU`, `YT` | `ON`                           | 1.0+    |
| `cta`            |    N     | `<string>`                                                             | `Get This Mortgage`            | 1.3+    |
| `link`           |    N     | `<uri>`                                                                | `https://my.thinkhomewise.com` | 1.3+    |
| `linkParameters` |    N     | `{name:value}`                                                         | `{}`                           | 1.14+   |
| `linkFragments`  |    N     | `{name:value}`                                                         | `{}`                           | 1.14+   |
| `rental`         |    N     | `no`, `mixed`, `filtered`                                              | `no`                           | 1.4+    |
| `mortgageType`   |    N     | `purchase`, `refinance`, `switch`                                      | `purchase`                     | 1.5+    |
| `rateType`       |    N     | `any`, `fixed`, `variable`                                             | `fixed`                        | 1.7+    |
| `price`          |    N     | `80000` - `100000000`                                                  | `650000`,`1000000`             | 1.5+    |
| `downPayment`    |    N     | `0` - `100000000`                                                      | `90000`, `200000`              | 1.5+    |
| `balance`        |    N     | `0` - `100000000`                                                      | `130000`                       | 1.5+    |
| `term`           |    N     | `any`, `1`,`2`,`3`,`4`,`5`,`7`,`10`                                    | `any`                          | 1.6+    |
| `lenderType`     |    N     | `any`, `bank`, `monoline`, `credit_union`                              | `any`                          | 1.6+    |
| `creditScore`    |    N     | `any`, `300_649`, `650_900`                                            | `650_900`                      | 1.7+    |
| `featureCount`   |    N     | `0` - `10`                                                             | `3`                            | 1.10+   |
| `hide`           |    N     | `lenderType`, `term`, `creditScore`                                    | `[]`                           | 1.8+    |
| `lenderName`     |    N     | `[<string>]`                                                           | `[]`                           | 1.9+    |
| `style`          |    N     | `table`, `card`                                                        | `table`                        | 1.10+   |

> [!TIP]
> Configure product table array with empty objects to render product tables(s) using default values. E.g. `homewise.productTable = [{},{},{}]`

##### Notes
* `bg` - Set default background color. Consider accessibility concerns when selecting the colour.
* `primaryColor` - Set default primary color. This sets colors for buttons and borders. Consider accessibility concerns when 
  selecting the colour.
* `font` - Toggle standard font load. `false` will allow you to apply the font used your website's CSS.
* `intro` - Toggle leading headline and introduction copy. Customization is not allowed, but by toggling you can position
  your own copy before the app embed container and make it seamless.
* `province` - Set default province selection.
* `cta` - Set default CTA label. Provided value is converted to uppercase automatically.
* `link` - Set a custom click through URL (_Read the points below if it leads to a page with Homewise mortgage
  application embed_).
  * Are you using the latest [mortgage application embed](../mortgage_application/embed.md)?
    * **Yes** - Great! You are all set.
    * **No** - Make sure you handle following query string parameters as described below.
      * `hw_product` URL variable must be captured and send back to embedded app as `hw_product` URL variable.
      * `hw_state` URL variable must be captured and send back to embedded app as `hw_state` URL variable.
      * `hw_segment` URL variable must be captured and send back to embedded app as part of the path before `/embed` bit.
        * _e.g. **With** `hw_segment` - `https://my.thinkhomewise.com/<partner_type>/<partner_code>/<hw_segment>/embed?hw_product=<hw_product>&hw_state=<hw_state>` 
         (`https://my.thinkhomewise.com/p/foo/bar/embed?hw_product=prod456&hw_state=aBc753dEf`)._
        * _e.g. **Without** `hw_segment` - `https://my.thinkhomewise.com/<partner_type>/<partner_code>/embed?hw_product=<hw_product>&hw_state=<hw_state>`
         (`https://my.thinkhomewise.com/p/foo/embed?hw_product=prod456&hw_state=aBc753dEf`)._
* `linkParameters` - Additional URL query string parameters you want to share with the destination page or with Homewise 
  to capture and report back to you. 
* `linkFragments` - Additional URL path fragments you want to share with the destination page or with Homewise to capture 
  and report back to you.
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
* `term` - Set default rate term (in years).
* `lenderType` - Set default lender type.
* `creditScore` - What type of lenders and rates to show. Score of 650+ for A-type. Score below 650 for B-type.
* `featureCount` - Limit (or increase) the number of features listed in bullet form. Value `0` will completely hide features.
* `hide` - Define the UI controls you want hidden. Default or set values from configuration is used in search.
* `lenderName` - Provide a list of lender codes to filter the results by. Your Homewise contact will provide this list to you.
* `style` - How to render the layout. Supports HTML table style or a modern card layout.

#### Example
```html
<script>
  var homewise = {
    partner: {
      type: "p",
      code: "partner_code_goes_here",
      segment: "optional_segment_goes_here"
    },
    productTable: [
      {
        bg: "#fff7ed",
        primaryColor: "#ff824d",
        font: false,
        intro: false,
        province: "BC",
        cta: "Learn More",
        link: "https://domain.com/page?foo=123&bar=456",
        linkParameters: { client_id:"abc123", client_src:"btn_click" },
        linkFragments: { scrollTo:"body_copy" }
        rental: "mixed",
        mortgageType: "purchase",
        rateType: "fixed",
        price: 650000,
        downPayment: 90000,
        balance: 130000,
        term: "3",
        lenderType: "credit_union",
        creditScore: "any",
        featureCount: 2,
        hide: ["lenderType", "term", "creditScore"]
      },
      {
        bg: "#fff7ed",
        primaryColor: "#ff824d",
        font: false,
        intro: true,
        province: "ON",
        cta: "Learn More",
        linkParameters: { client_id:"abc123", client_src:"btn_click" },
        linkFragments: { scrollTo:"body_copy" }
        rental: "mixed",
        mortgageType: "refinance",
        rateType: "any",
        price: 650000,
        downPayment: 90000,
        balance: 130000,
        term: "4",
        lenderType: "monoline",
        creditScore: "650_900",
        featureCount: 4,
        hide: ["lenderType"],
        lenderName: ["rfa","td"],
        style: "card"
      }
    ]
  };
</script>
<script src="https://widgets.thinkhomewise.com/lib/com-product-table/1.14/embed.js"></script>
```

### Step 5 - Optional
Call your custom functions (e.g. web analytics, product analytics) by listening to widget's native events. Following events are available.

| Event                           | Description                                           | Version |
|---------------------------------|-------------------------------------------------------|---------|
| `hw_product_table_search_click` | Fires per search button click, per instance.          | 1.10+   |
| `hw_product_table_rate_click`   | Fires per rate search result CTA click, per instance. | 1.10+   |

#### Example
```html
<script>
  var homewise = {...};
</script>
<script src="https://widgets.thinkhomewise.com/lib/com-product-table/1.14/embed.js"></script>
<script>
  window.addEventListener("hw_product_table_search_click", (e) => {
    console.log(e.detail);
  });
  window.addEventListener("hw_product_table_rate_click", (e) => {
    console.log(e.detail);
  });
</script>
```

#### Event Details
Event's detail object (refer to `e.detail` above) is available to use. Schemas are shown below. 

##### Schema - `hw_product_table_search_click` 
```json lines
{
  "className": <string>,
  "index": <string>,
  "balance": <number>,
  "borrowing": <number>,
  "creditScore": <string>,
  "downPayment": <number>,
  "hide": [<string>],
  "isRental": <boolean>,
  "lenderName": [<string>],
  "lenderType": <string>,
  "mortgageType": <string>,
  "price": <number>,
  "province": <string>,
  "rateType": <string>,
  "rentalToggle": <string>,
  "term": <string>
}
```

##### Schema - `hw_product_table_rate_click`
```json lines
{
  "className": <string>,
  "index": <string>,
  "legal_name": <string>,
  "lender": <string>,
  "payment": <number>,
  "rate_value": <number>,
  "term": <number>
}
```

### Step 6 - Optional
This section outlines the class structure and hierarchy for the components used in this project. It also includes 
specific wrapping divs, which are named by index (e.g., `homewise_product_table_{your-index}`) and have an ID based on 
the device type (e.g., `homewise_product_table_d` for desktop or `homewise_product_table_m` for mobile). Use this as a 
reference when developing or updating styles.

#### 1. Card Component
The `hw__card` component displays key product information. It is divided into three main sections:

- **Content (`hw__content`)**: Contains the logo, product details, and rate information.
- **Action (`hw__action`)**: Houses buttons or actions like "Apply Now."
- **Accordion (`hw__accordion`)**: Additional expandable information.
```
hw__card
  ├── hw__content
  │     ├── hw__logo
  │     │     └── hw__logo-image (e.g., lender's logo)
  │     ├── hw__details
  │     │     ├── hw__features
  │     │     │     └── ul > li (list of features like "Cashback")
  │     │     ├── hw__rate
  │     │     │     ├── hw__h2 (rate value, e.g., 5.25%)
  │     │     │     └── small (rate description)
  │     │     ├── hw__monthly
  │     │           ├── hw__h2 (monthly payment amount)
  │     │           └── small (e.g., "per month")
  ├── hw__action
  └── hw__accordion
        └── hw__accordion-ul
              └── li (each expandable item)
```

#### 2. Table Body (Desktop View)
The `hw__table-body` displays product information in a tabular format for larger screens.
```
hw__table-body
  ├── hw__logo-image (e.g., lender's logo)
  ├── hw__legal-name (e.g., lender's full name)
  ├── hw__product-name (e.g., product name)
  ├── hw__features
  │     └── ul > li (list of product features)
  ├── hw__rate
  │     ├── h4 (e.g., 5.25%)
  │     └── small (rate type, e.g., "Fixed")
  ├── hw__term
  │     ├── h4 (term length, e.g., "5 years")
  │     └── small (additional term info)
  ├── hw__payment
  │     ├── h4 (e.g., $1,250)
  │     └── small (e.g., "per month")
  └── hw__action (e.g., button for "More Info")
```

#### 3. Table Body (Mobile View)
The `hw__table-mobile` adapts the table structure for smaller screens. Key details are presented compactly.
```
hw__table-mobile
  ├── hw__table-body-mobile
  │     ├── hw__table-mobile-lender
  │     │     ├── hw__logo-image (e.g., lender's logo)
  │     │     └── hw__product-name (e.g., product name)
  │     └── hw__table-mobile-action
  │           ├── p (rate details)
  │           ├── small (term and rate type)
  │           ├── h4 (payment amount)
  │           └── small (e.g., "per month")
```

## Support
Contact Homewise Solutions Inc. at *hello[at]thinkhomewise.com* for support. Feel free to report any bugs you find via 
email or on GitHub.

**© Homewise Solutions Inc. All rights reserved.**

[Privacy Policy](https://thinkhomewise.com/page/privacy/) | [Terms of Agreement](https://thinkhomewise.com/page/term/).
