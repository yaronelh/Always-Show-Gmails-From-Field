# Always Show Gmails From Field

This Chrome extension, Keeps the from field always visible, making it easier to see and confirm the email account you're using to send emails.
the default behavior of Gmail and Google workspaces is to have the From field Hidden the second you start writing your email This keeps it visible all the time.


## What is this extension?

This extension is extremely simple. It only includes 3 lines of css.

```css
.I5 .fX.aiL {
  display: block !important;
}
```

That's it🙂

**Of course you have your manifest, which is mandatory **

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

- Go to the three dots next to your profile. From the menu drop down, select extensions > manage extensions
- Then activate developer mode from the top right, A few more options will be added to the extensions page 
- Choose load unpacked

  ![image](https://github.com/yaronelh/Always-Show-Gmails-From-Field/assets/7690499/3132fe7c-d8e3-4d3f-9e91-5a7c18410ebe)

- and choose the folder you created with the two files. 

Alternatively, you can download the ready made files I created and point chrome to that.
(This would work on any chromium-based browser), Now you can finally see the from field, especially if you have multiple from options when you're typing and preparing the email.
hopefully the development team at Gmail will add this feature in the future but currently it doesn't exist, so that's a quick workaround 😉.




