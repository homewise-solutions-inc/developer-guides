# Embed Homewise Affordability Calculator
Thank you for partnering with Homewise!

This guide covers the steps to embed Homewise Affordability calculator into your website.

## Installation

### Step 1
Complete [partner configuration](../partner/configuration.md).

### Step 2
Paste following line right after the `homewise` object. This loads the widget embed script.

```html
<script src="https://widgets.thinkhomewise.com/lib/com-affordability-calculator/1.3/embed.js"></script>
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
<script src="https://widgets.thinkhomewise.com/lib/com-affordability-calculator/1.3/embed.js"></script>
```

#### Versions
Homewise will release versions time to time introducing new features and bug fixes. We recommend that you use the latest 
version of embed script by changing the version number (e.g `/1.3/embed.js`). Following table shows available versions.

| Version | Notes                                                                   |
|:-------:|-------------------------------------------------------------------------|
|   1.3   | First version with all launch features.                                 |


### Step 3
Paste following code where you want the Homewise Affordability calculator to appear.
```html
<div class="homewise_affordability_calculator"></div>
```

### Step 4 - Optional
Optionally, customize the calculator by adding `affordabilityCalculator` configuration object to the `homewise` 
default object.
> :warning: Please refer to browser's console for errors.

```html
<script>
  var homewise = {
    partner: { ... },
    affordabilityCalculator: {
      bg: <string>
    }
  };
</script>
```

#### Reference
| Property       | Required | Accepted Values                                                        | Default                        |
|----------------|:--------:|------------------------------------------------------------------------|--------------------------------|
| `bg`           |    N     | *Any hexadecimal color code.*                                          | `#ffffff`                      |

##### Notes
* `bg` - Set default background color. Consider accessibility concerns when selecting the colour.

#### Example
```html
<script>
  var homewise = {
    partner: {
      type: "p",
      code: "foo",
      segment: "bar"
    },
    affordabilityCalculator: {
      bg: "#fff7ed"
    }
  };
</script>
<script src="https://widgets.thinkhomewise.com/lib/com-affordability-calculator/1.3/embed.js"></script>
```

## Support
Contact Homewise Solutions Inc. at *hello[at]thinkhomewise.com* for support. Feel free to report any bugs you find via 
email or on GitHub.

**© Homewise Solutions Inc. All rights reserved.**

[Privacy Policy](https://thinkhomewise.com/page/privacy/) | [Terms of Agreement](https://thinkhomewise.com/page/term/).







