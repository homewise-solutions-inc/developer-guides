# Embed Homewise Mortgage Application
Thank you for partnering with Homewise!

This guide covers the steps to embed Homewise application process into any website using Homewise Partner code.

## Installation

### Step 1
Go to [https://homewisepartners.com/](https://homewisepartners.com/) and apply to become a Homewise Partner. 
If you are having trouble registering, please Contact us at *hello[at]thinkhomewise.com*.

### Step 2
1. Log into your partner dashboard.
2. Copy the partner code provided to you (this will be use as `{partner_code}` at Step 3)

### Step 3
#### Method 1
Paste the following code with **correct values** where you want the embed to appear.

<pre>
<iframe id="homewise" src="https://my.thinkhomewise.com/partner/<b>{partner_code}</b>/embed" frameborder="0" border="0"></iframe>
</pre>

#### Method 2 (Recommended)
1. Download [iFrameResizer](../files/iframeSizer.min.js.zip).
2. Unzip it and upload `iframeSizer.min.js` file to your web server.
3. Paste the following code with **correct values** (file path & partner code) where you want the embed to appear.

<pre>
<script src="https://example.com/path/to/iframeResizer.min.js"></script>
<style>iframe { width: 1px; min-width: 100%; }</style>
<iframe id="homewise" src="https://my.thinkhomewise.com/partner/{partner_code}/embed" frameborder="0" border="0"></iframe>
<script>iFrameResize({ heightCalculationMethod: 'max', resizeFrom: 'child' }, '#homewise');</script>
</pre>

Note: [iFrameResizer](https://github.com/davidjbradshaw/iframe-resizer) is used to dynamically resize 
the `<iframe/>` height based on content. Homewise tested this combination for proper functionality. 
   
## Support
Contact Homewise Solutions Inc. at *hello[at]thinkhomewise.com* for support. Feel free to report any bugs you find via 
email or on GitHub.

**© Homewise Solutions Inc. All rights reserved.**

[Privacy Policy](https://thinkhomewise.com/page/privacy) | [Terms of Agreement](https://thinkhomewise.com/page/terms).
