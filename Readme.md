# closeheat docs

This is the start of the docs. The famous first words.


# Integrations
## Segment

Segment.com is an integration hub, which helps you add other integrations more easily. It lets you enable Google Analytics, Mixpanel and a lot of others in a flick of a switch.

You can easily integrate Segment with closeheat.

### Sign up

Head to [Segment.com](https://segment.com) and sign up for free.

### Create a project

Click "New project" in the top right. It will ask you the name and URL of an your app.
Fill it with your closeheat information - f.e. "my-awesome-app" and "http://my-awesome-app.closeheatapp.com"

### Get your integration code

After creating a project, click on "Install a library on your site or mobile app".

Make sure you have "Browser" tab selected in the top and you should see your integration code:

```html
<script type="text/javascript">
!function(){var analytics=window.analytics=window.analytics||[];if(!analytics.initialize)if(analytics.invoked)window.console&&console.error&&console.error("Segment snippet included twice.");else{analytics.invoked=!0;analytics.methods=["trackSubmit","trackClick","trackLink","trackForm","pageview","identify","group","track","ready","alias","page","once","off","on"];analytics.factory=function(t){return function(){var e=Array.prototype.slice.call(arguments);e.unshift(t);analytics.push(e);return analytics}};for(var t=0;t<analytics.methods.length;t++){var e=analytics.methods[t];analytics[e]=analytics.factory(e)}analytics.load=function(t){var e=document.createElement("script");e.type="text/javascript";e.async=!0;e.src=("https:"===document.location.protocol?"https://":"http://")+"cdn.segment.com/analytics.js/v1/"+t+"/analytics.min.js";var n=document.getElementsByTagName("script")[0];n.parentNode.insertBefore(e,n)};analytics.SNIPPET_VERSION="3.0.1";
analytics.load("h1NSpsqTEjGZPc25fPyIrzMpfDCm491y");
analytics.page()
}}();
</script>
```

### Add integration code to your closeheat landing page via in-browser editor

Make sure you are logged in closeheat and open your landing page (f.e. "http://my-awesome-app.closeheatapp.com").

Look in the lower right corner for closeheat logo and click it. Doing that will open an in-browser editor.

Look for ``</head>`` closing tag and put your segment code right above it. For example:

```html
<head>
<title>My Awesome Website</title>
<script type="text/javascript">
!function(){var analytics=window.analytics=window.analytics||[];if(!analytics.initialize)if(analytics.invoked)window.console&&console.error&&console.error("Segment snippet included twice.");else{analytics.invoked=!0;analytics.methods=["trackSubmit","trackClick","trackLink","trackForm","pageview","identify","group","track","ready","alias","page","once","off","on"];analytics.factory=function(t){return function(){var e=Array.prototype.slice.call(arguments);e.unshift(t);analytics.push(e);return analytics}};for(var t=0;t<analytics.methods.length;t++){var e=analytics.methods[t];analytics[e]=analytics.factory(e)}analytics.load=function(t){var e=document.createElement("script");e.type="text/javascript";e.async=!0;e.src=("https:"===document.location.protocol?"https://":"http://")+"cdn.segment.com/analytics.js/v1/"+t+"/analytics.min.js";var n=document.getElementsByTagName("script")[0];n.parentNode.insertBefore(e,n)};analytics.SNIPPET_VERSION="3.0.1";
analytics.load("h1NSpsqTEjGZPc25fPyIrzMpfDCm491y");
analytics.page()
}}();
</script>
</head>
```

Once the code is in place - click "Publish" and make sure you get no errors. Segment.com is installed on your landing page once the deployment is done.

### Check to see it works or debug errors

Head to Segment.com and click on the debugger tab in the top navigation bar. It shows all logged actions that were made on your landing page.

Having the debugger opened in one tab, open your landing page in another tab (f.e. "http://my-awesome-app.closeheatapp.com").

If the integration is working - it will log all the page loads by showing "Page /".
