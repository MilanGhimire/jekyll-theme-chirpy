---
title: TempData is always null
author: Milan Ghimire
date: 2020-06-05 20:32:05 +05:45
categories: [ASP.NET Core]
tags: [tempdata]
---

I was using TempData for the submission for the data and send mail. Then pass through the TempData to HTML whether the form submission and mail send was successful or not.

To show the message I use toastr for showing the message.

This is the CDN for using toastr. Which I used.

```html
<link href="https://cdnjs.cloudflare.com/ajax/libs/toastr.js/2.0.1/css/toastr.css" rel="stylesheet" />
<script src="https://cdnjs.cloudflare.com/ajax/libs/toastr.js/2.1.4/toastr.min.js"></script>
````

This is the JS code to show the toastr.

```js
toastr.success('Successfully message.');
```

But I was not getting the TempData. Instead it was always null. So I researched and tried many options.

#### There are 2 solutions

##### 1. Make Cookie essential

Later I found one stackoverflow post. which gave me the solution. Add below code to Startup.cs

```
// The Tempdata provider cookie is not essential. Make it essential
// so Tempdata is functional when tracking is disabled.
services.Configure<CookieTempDataProviderOptions>(options => {
      options.Cookie.IsEssential = true;
});
```

So we need to make the Cookie as essential.

##### 2. Accept the message
Add this to your page.

```
<partial name="_CookieConsentPartial" />
```

This will show message which shows up like this.

![Asp.net Core Cookie policy accept]({{{ "assets/img/post/cookie-accept-asp-net-core.png" | relative_url }}})

and if we accept this then the TempData will work.

#### Conclusion
TempData uses cookie which is disabled by ASP.NET Core as default. So we can achieve either making
it essential or giving message to accept the cookie.