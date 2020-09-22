# Embed Homewise Mortgage Application
Thank you for partnering with Homewise!

This guide covers the steps to embed Homewise application process into any website using Homewise Partner code.

## Installation

### Step 1
Go to [https://homewisepartners.com/](https://homewisepartners.com/) and apply to become a Homewise Partner. 
If you are having trouble registering, please Contact us at *hello[at]thinkhomewise.com*.

### Step 2
Once you are approved, get the code from your dashboard.

### Step 3
#### Method 1
Paste the following code with ***correct values*** where you want the embed to appear.

<pre>
<iframe id="homewise" src="https://my.thinkhomewise.com/partner/<b>{partner_code}</b>/embed" frameborder="0" border="0"></iframe>
</pre>

#### Method 2 (Recommended)
Follow method 1 above along with [iFrameResizer](http://davidjbradshaw.github.io/iframe-resizer/) to dynamically resize 
the `<iframe/>` height based on content. Homewise tested this combination for proper functionality.

Paste the following code with ***correct values*** where you want the embed to appear.

<pre>
<script src="<b>https://example.com/path/to/</b>iframeResizer.min.js"></script>
<style>iframe { width: 1px; min-width: 100%; }</style>
<iframe id="homewise" src="https://my.thinkhomewise.com/partner/<b>{partner_code}</b>/embed" frameborder="0" border="0"></iframe>
<script>iFrameResize({ heightCalculationMethod: 'max', resizeFrom: 'child' }, '#homewise');</script>
</pre>
   
## Support
Contact Homewise Solutions Inc. at *hello[at]thinkhomewise.com* for support. Feel free to report any bugs you find via 
email or on GitHub.

**© Homewise Solutions Inc. All rights reserved.**

[Privacy Policy](https://thinkhomewise.com/page/privacy) | [Terms of Agreement](https://thinkhomewise.com/page/terms).
