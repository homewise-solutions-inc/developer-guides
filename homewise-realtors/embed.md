# Embed Homewise Mortgage Application
Thank you for partnering with Homewise!

This guide covers the steps to embed Homewise application process into any website using Homewise Realtor code.

## Installation

### Step 1
Go to [https://homewiserealtors.ca](https://homewiserealtors.ca) and apply to become a Homewise Realtor. 
If you are having trouble registering, please Contact us at *hello[at]thinkhomewise.com*.

### Step 2
1. Log into your realtor dashboard.
2. Copy the partner code provided to you (this will be use as `{partner_code}` at Step 3).

### Step 3
#### Method 1
Paste the following code with correct values where you want the embed to appear.

```
<iframe id="homewise" src="https://my.thinkhomewise.com/r/{realtor_code}/embed" frameborder="0" border="0" width="{width}" height="{height}"></iframe>
```

#### Method 2
1. Download [iFrameResizer](../files/iframeSizer.min.js.zip).
2. Unzip it and upload `iframeSizer.min.js` file to your web server.
3. Paste the following code with **correct values** (file path & partner code) where you want the embed to appear.

```
<script src="https://yourdomain.com/path/to/iframeResizer.min.js"></script>
<style>iframe { width: 1px; min-width: 100%; }</style>
<iframe id="homewise" src="https://my.thinkhomewise.com/r/{realtor_code}/embed" frameborder="0" border="0"></iframe>
<script>iFrameResize({ heightCalculationMethod: 'max', resizeFrom: 'child' }, '#homewise');</script>
```

Note: [iFrameResizer](https://github.com/davidjbradshaw/iframe-resizer) is used to dynamically resize
the `<iframe/>` height based on content. Homewise tested this combination for proper functionality.

#### Reference
Use the reference table below to understand the embed parameters better.

Parameter        | Description                      | Example
---------------- | -------------------------------- | -------- 
`{realtor_code}` | Unique realtor code. See Step 2. | `abc123`
`{width}`        | Width of embed in pixels.        | `950`
`{height}`       | Height of embed in pixels.       | `800`
   
## Support
Contact Homewise Solutions Inc. at *hello[at]thinkhomewise.com* for support. Feel free to report any bugs you find via 
email or on GitHub.

**© Homewise Solutions Inc. All rights reserved.**

[Privacy Policy](https://thinkhomewise.com/page/privacy) | [Terms of Agreement](https://thinkhomewise.com/page/terms).