---
description: Specific how to edit and use constraints in WordPress.
---

# kbase.us

## Responsive Image Sizing

For webpages viewed on a larger screen i.e., computer, the maximum width is 800px.&#x20;

If image width is greater than 800px

`width=”100%” height=”auto”`

If width is less than 800px

`max-width=”100%” height=”auto”`

If width is not 800px or greater, but you want to set a specific maximum size.&#x20;

`width=”100%” max-width=”nnnpx” height=”auto”`

## Creating boxes around text

`<p style="border: Npx; border-style:solid; border-color: #HTMLtag; padding: 1em;"> text here </p>`

Teal boxes for developer highlights are 5px and #009688.&#x20;

## Stop text from wrapping around an align left image

```
<br clear="left">
```

## Pop up messages

Best practices for using Hustle for messaging on kbase.us

1. Add or edit descriptive Title including dates.
2. Include informative Main Content.&#x20;
3. Add enable the "Never see this message again" link
4. Optional, schedule specific dates, but revert to "Draft" after maintenance period.&#x20;
5. Publish!
