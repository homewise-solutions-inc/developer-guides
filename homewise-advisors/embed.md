# Embed Homewise Mortgage Application
Thank you for partnering with Homewise!

This guide covers the steps to embed Homewise application process into any website using Homewise Advisor code.

## Installation

### Step 1
Go to [https://homewiseadvisors.com/](https://homewiseadvisors.com/) and apply to become a Homewise Advisor. 
If you are having trouble registering, please Contact us at *hello[at]thinkhomewise.com*.

### Step 2
Once you are approved, get the code from your dashboard.

### Step 3
#### Method 1
Paste the following code with correct values where you want the embed to appear.

```
<iframe id="homewise" src="https://my.thinkhomewise.com/advisor/{advisor_code}/embed" frameborder="0" border="0"></iframe>
```

#### Method 2 (Recommended)
Follow method 1 above along with [iFrameResizer](http://davidjbradshaw.github.io/iframe-resizer/) to dynamically resize 
the `<iframe/>` height based on content. Homewise tested this combination for proper functionality.

Paste the following code with correct values where you want the embed to appear.

```
<script src="https://example.com/path/to/iframeResizer.min.js"></script>
<style>iframe { width: 1px; min-width: 100%; }</style>
<iframe id="homewise" src="https://my.thinkhomewise.com/advisor/{advisor_code}/embed" frameborder="0" border="0"></iframe>
<script>iFrameResize({ heightCalculationMethod: 'max', resizeFrom: 'child' }, '#homewise');</script>
```
   
## Support
Contact Homewise Solutions Inc. at *hello[at]thinkhomewise.com* for support. Feel free to report any bugs you find via 
email or on GitHub.

**© Homewise Solutions Inc. All rights reserved.**

[Privacy Policy](https://thinkhomewise.com/page/privacy) | [Terms of Agreement](https://thinkhomewise.com/page/terms).