---
description: Customer Relations Management for AC0/RD
---

# Customer Relations

## Customerly

Thanks to Github Education, we've been able to use Customerly for the next 6 months to try it out. Customerly is a live-chat & CRM tool that we can embed onto our sites. It will not be embedded on the main site \(http://acord.software\) for the time being, as we're still debating the usefulness of Facebook Messenger - remember, a huge influx of new members for 2020 were sent to us from our Facebook Page. We'll be embedding it on our Tumblr Blog for now.

```
<!-- Customerly Integration Code -->
<script>
    window.customerlySettings = {
        app_id: "bb4ed313"
    };
    !function(){function e(){var e=t.createElement("script");
    e.type="text/javascript",e.async=!0,
    e.src="https://widget.customerly.io/widget/bb4ed313";
    var r=t.getElementsByTagName("script")[0];r.parentNode.insertBefore(e,r)}
    var r=window,t=document,n=function(){n.c(arguments)};
    r.customerly_queue=[],n.c=function(e){r.customerly_queue.push(e)},
    r.customerly=n,r.attachEvent?r.attachEvent("onload",e):r.addEventListener("load",e,!1)}();
</script>
```

{% hint style="info" %}
This code can be embedded on any HTML page, but please check with us before you insert it anywhere
{% endhint %}

### What we need to do

* [x] Create customerly account
* [ ] Embed in Bootstrap site
* [ ] Connect to Slack \(we need to find a chat plugin that incorporates with slack\)

