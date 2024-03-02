# Always Show Gmails From Field

This Google Chrome extension keeps the from field always visible, making it easier to see and confirm the email account you're using to send emails.
Especially when you're in the process of editing the email. The default behavior of Gmail and Google workspaces is to have the from field hidden the second you start writing your email, this forces it to be visible all the time.
this little trick would work on any chromium-based browser.

## Why does it need to be an extension?

Since we need this change to be applied each time we visit the Gmail page. The only way to do that is through an extension.
If we don't do that, Gmail will revert to its default behavior the next time you refresh the page, So, to keep the from field always visible we need a mechanism that will activate each time you open a Gmail and that is only possible through extensions.

## What in the extension?

Well, this extension is only 3 lines of css, so it's not much of an extension, but we need the persistency (visible all the time), so we have to go with the extension approach.
Let's get to the point as it takes less time to implement than explain.

These are the three lines of CSS we need, they need to be in their own file.

```css
.I5 .fX.aiL {
  display: block !important;
}

.I5 .aoD.hl {
  display: none;
}
```

That's it🙂

**Of course you have your manifest, which is mandatory**

Then we have the manifest.json The purpose of the manifest is to point to that CSS file,  ```"css": ["gmail.css"]``` and for it to be only activated when We're in Gmail ```"matches": ["https://mail.google.com/*"]```.
The entire json file looks like this:


```json
{
    "manifest_version": 2,
    "name": "Always Show Gmails From Field",
    "version": "1.0",
    "description": "Always Show 'from' field in Gmail when editing the email when editing your email .",
    "permissions": ["activeTab", "https://mail.google.com/"],
    "content_scripts": [
      {
        "matches": ["https://mail.google.com/*"],
        "css": ["gmail.css"]
      }
    ]
  }
```

## How to get it working locally 

Technically you can do this process manually, Just create a folder and create two additional files, one named manifest.json and one named gmail.css

Then follow these steps:

1. Go to the three dots next to your profile. From the menu drop down, select extensions > manage extensions
2. Then activate developer mode from the top right, A few more options will be added to the extensions page 
3. Choose load unpacked
![image](https://github.com/yaronelh/Always-Show-Gmails-From-Field/assets/7690499/3132fe7c-d8e3-4d3f-9e91-5a7c18410ebe)
4. Choose the folder you created with the two files. 

Alternatively, you can download the folder "Gmail From Field Extension" I created at the top and point chrome to that.
(This would work on any chromium-based browser), Now you can finally see the from field, especially if you have multiple from options when you're typing and preparing the email.
hopefully the development team at Gmail will add this feature in the future but currently it doesn't exist, so that's a quick workaround 😉.
