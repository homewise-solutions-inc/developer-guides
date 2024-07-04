# Homewise Partner Configuration for Embeds
Thank you for [partnering with Homewise](https://youtu.be/yz-ZVXk6R2k)! Remember, there are
[multiple ways to share](https://www.youtube.com/watch?v=m2HKbYtsZl8) your personalized URL or widgets!

This documentation covers the steps you should take before embedding any Homewise widgets that are publicly available.
Thank you for interest with Homewise!

## Installation
Following steps covers how to add the Homewise partner configuration to your website. Please note that for this process 
you will need help from a web developer.

### Step 1
Contact Homewise at *hello[at]thinkhomewise.com* to work out your partnership contract. We recommend and love to talk
with you to understand the partnership better.

Now, based on your business type, register at one of our partner portals below to get your partner code which is 
available on partner dashboard.
- Homewise for Advisors: [https://homewiseadvisors.com](https://homewiseadvisors.com/) - applies to following businesses:
  - Financial Advisor
  - Financial Planner
  - Insurance Advisor
  - Investment Advisor
  - Personal Banker
  - Other (any industry closely related to above categories)
- Homewise for Partners: [https://homewisepartners.com](https://homewisepartners.com/) - applies to following businesses:
  - Professional Services
  - Technology/Startup
  - Real Estate Development
  - Insurance
  - Other (any industry closely related to above categories)
- Homewise for Realtors: [https://homewiserealtors.ca](https://homewiserealtors.ca) - applies to following businesses:
  - Residential Resale
  - Residential Pre-Construction
  - Commercial
  - Other (any industry closely related to above categories)

Are you a blogger? a news site? or simply having trouble deciding which partner portal to register on? Contact Homewise
at *hello[at]thinkhomewise.com*. We can help you.

### Step 2
1. Log into your partner dashboard.
2. Copy the partner code.

### Step 3
Paste the following code somewhere near top of the page. Right before `</head>` tag or right after `<body>` tag is 
recommended. Fill it with correct values. This adds Homewise default configuration matching your unique partner details.

> :warning: Completing this step with correct values is crucial. Please refer to browser's console for errors.

```html
<script>
  var homewise = {
    partner: {
      type: <string>,
      code: <string>,
      segment: <string>
    }
  };
</script>
```

#### Reference
| Property   | Required | Accepted Values               | Default  |
|------------|:--------:|-------------------------------|----------|
| `type`     |    Y     | `p`, `a`, `r`                 | `null`   |
| `code`     |    Y     | `a-z`, `A-Z`, `0-9`, `-`, `_` | `null`   |
| `segment`  |    N     | `a-z`, `A-Z`, `0-9`, `-`, `_` | `null`   |

##### Notes
* `type` - Your partner type. Partner (`p`), Advisor (`a`) or Realtor (`r`).
* `code` - Partner code copied from your partner dashboard _or_ a code Homewise generated for you.
* `segment` - Value to associate with the collected mortgage application. Visible in the dashboard (or custom reports). 
  * _E.g. You built 2 pages with Homewise app embedded. One page is for Ontario and one page is for Alberta. You can use
    `ontario` and `alberta` as segment values. This will allow us segment apps differently in reports._

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
```

### Step 4 (Optional)
If there is a [Content Security Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP) used on your website 
make sure to update it to include following policy. 
```
"base-uri 'self';
connect-src 'self' https://*.sentry.io/ https://*.thinkhomewise.com ;
font-src 'self' data: https://fonts.googleapis.com https://fonts.gstatic.com ;
form-action 'self';
frame-ancestors 'self';
frame-src 'self' ;
img-src 'self' data: https:;
media-src 'self' ;
object-src 'self' ;
script-src 'self' 'unsafe-inline' 'unsafe-eval' *.googleapis.com https://*.thinkhomewise.com;
style-src 'self' 'unsafe-inline' https://fonts.googleapis.com;"
```

## Support
Contact Homewise Solutions Inc. at *hello[at]thinkhomewise.com* for support. Feel free to report any bugs you find via
email or on GitHub.

**© Homewise Solutions Inc. All rights reserved.**

[Privacy Policy](https://thinkhomewise.com/page/privacy/) | [Terms of Agreement](https://thinkhomewise.com/page/terms/).