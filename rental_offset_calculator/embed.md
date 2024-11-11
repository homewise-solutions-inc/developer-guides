# Embed Homewise Affordability Calculator with Rental Offset/Add-Back
Thank you for [partnering with Homewise](https://youtu.be/yz-ZVXk6R2k)! Remember, there are
[multiple ways to share](https://www.youtube.com/watch?v=m2HKbYtsZl8) your personalized URL or widgets!

This guide covers the steps to embed Homewise Affordability calculator with rental offset/add-back options into your website.

## Installation

### Step 1
Complete [partner configuration](../partner/configuration.md).

### Step 2
Paste following line right after the `homewise` object. This loads the widget embed script.

```html
<script src="https://widgets.thinkhomewise.com/lib/com-rental-offset-calculator/1.0/embed.js"></script>
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
<script src="https://widgets.thinkhomewise.com/lib/com-rental-offset-calculator/1.0/embed.js"></script>
```

#### Versions
Homewise will release versions with new features and bug fixes. We recommend that you use the latest 
version of embed script by changing the version number (e.g `/1.0/embed.js`). Following table shows available versions.

| Version | Notes                                                                   |
|:-------:|-------------------------------------------------------------------------|
|   1.0   | First version with all launch features.                                 |


### Step 3
Paste following code where you want the widget to appear.
```html
<div class="homewise_rental_offset_calculator"></div>
```

### Step 4 - Optional
Optionally, customize the calculator by adding `rentalOffsetCalculator` configuration object to the `homewise` 
default object.
> :warning: Please refer to browser's console for errors.

```html
<script>
  var homewise = {
    partner: { ... },
    rentalOffsetCalculator: {
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
      code: "partner_code_goes_here",
      segment: "optional_segment_goes_here"
    },
    rentalOffsetCalculator: {
      bg: "#fff7ed"
    }
  };
</script>
<script src="https://widgets.thinkhomewise.com/lib/com-rental-offset-calculator/1.0/embed.js"></script>
```

## Support
Contact Homewise Solutions Inc. at *hello[at]thinkhomewise.com* for support. Feel free to report any bugs you find via 
email or on GitHub.

**© Homewise Solutions Inc. All rights reserved.**

[Privacy Policy](https://thinkhomewise.com/page/privacy/) | [Terms of Agreement](https://thinkhomewise.com/page/term/).







