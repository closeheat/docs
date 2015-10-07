# closeheat docs

This is the start of the docs. The famous first words.

# Designs

## Simple structure that works
Your landing page files should have a simple structure: an ``index.html`` file in its root directory.

- When you visit ``my-awesome-app.closeheatapp.com``, we will show you ``index.html``.
- If you visit ``my-awesome-app.closeheatapp.com/team.html``, we will show ``team.html``.
- If you visit ``my-awesome-app.closeheatapp.com/team``, we will show you ``team/index.html``.

You can use any structure you want, but the usual one is:

```
- index.html
- /team -
      - index.html
- /img -
     - logo.png
- /css -
     - hero.css
```

## How are files stored at closeheat?

closeheat serves all landing page files from GitHub. To import your custom design to closeheat means uploading your files to GitHub and adding that GitHub project to closeheat.

## Import custom design

You can import your own beautiful HTML / CSS landing page designs into closeheat. closeheat lets you to do it in a couple of ways. Using GitHub Client is the simplest way for somebody who does not use ``git``.

### Publishing your landing page files to GitHub

Follow [GitHub guide](https://guides.github.com/introduction/getting-your-project-on-github) and publish your landing page files to GitHub.

### Files structure
Make sure you have your ``index.html`` (or ``.jade``) in the root folder of your GitHub repository. All the ``require`` declarations in your javascript files will be downloaded upon build - so you don't need a ``package.json`` if you don't want. 
We're working on a custom build solution, so you can use whatever you want.

### Connect files in GitHub to closeheat

When you have your project files in GitHub - click [here](http://app.closeheat.com/apps/upload/github) and select you repository. Wait for the publishing to finish and check out your new landing page!

### Edit landing page locally
When you change files in you GitHub project, it also changes in your closeheat landing page. In fancy terms, it is called ``continuous deployment``.

You can edit your files on GitHub the way you like - whether its using Sublime Text or Notepad.


# Integrations
## Segment

Segment.com is an integration hub, which helps you add other integrations more easily. It lets you enable Google Analytics, Mixpanel and a lot of others in a flick of a switch.

You can easily integrate Segment with closeheat.

### Sign up with Segment

Head to [Segment.com](https://segment.com) and sign up for free.

### Create a project in Segment

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

Look for ``</head>`` closing tag and put your Segment code right above it. For example:

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

Once the code is in place - click "Publish" and make sure you get no errors.

Segment.com is installed on your landing page once the deployment is done.

### Check to see it works

Head to Segment.com and click on the debugger tab in the top navigation bar. It shows all logged actions that were made on your landing page.

Having the debugger opened in one tab, open your landing page in another tab (f.e. "http://my-awesome-app.closeheatapp.com").

If the integration is working - it will log all the page loads by showing "Page /".


## Capture leads with MailChimp

MailChimp lets you capture emails, design and send email marketing campaigns. They provide you a form you can embed on your landing page to build email lists.

### Sign up with MailChimp

Head to [MailChimp website](http://mailchimp.com) and create an account.

### Create a list on MailChimp

Click on "Lists" from the top navigation bar and "Create List" afterwards.

Choose a name for it (f.e. "My Awesome Newsletter") and fill all the missing information.

### Get embeddable form code from MailChimp

Click "Signup forms" in the menu and select "Embeddable forms" afterwards.

Customise the form so it fits your needs and then copy the code under section "Copy/paste onto your site". It will look like this:

```html
<!-- Begin MailChimp Signup Form -->
<link href="//cdn-images.mailchimp.com/embedcode/slim-081711.css" rel="stylesheet" type="text/css">
<style type="text/css">
	#mc_embed_signup{background:#fff; clear:left; font:14px Helvetica,Arial,sans-serif; }
	/* Add your own MailChimp form style overrides in your site stylesheet or in this style block.
	   We recommend moving this block and the preceding CSS link to the HEAD of your HTML file. */
</style>
<div id="mc_embed_signup">
<form action="//domasbitvinskas.us10.list-manage.com/subscribe/post?u=f84937ea3dcb3a0e8caee05e2&amp;id=a10d6d055b" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_blank" novalidate>
    <div id="mc_embed_signup_scroll">
	<label for="mce-EMAIL">Subscribe to our mailing list</label>
	<input type="email" value="" name="EMAIL" class="email" id="mce-EMAIL" placeholder="email address" required>
    <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->
    <div style="position: absolute; left: -5000px;"><input type="text" name="b_f84937ea3dcb3a0e8caee05e2_a10d6d055b" tabindex="-1" value=""></div>
    <div class="clear"><input type="submit" value="Subscribe" name="subscribe" id="mc-embedded-subscribe" class="button"></div>
    </div>
</form>
</div>

<!--End mc_embed_signup-->
```

### Add embeddable form code to your closeheat landing page via in-browser editor

Make sure you are logged in closeheat and open your landing page (f.e. "http://my-awesome-app.closeheatapp.com").

Look in the lower right corner for closeheat logo and click it. Doing that will open an in-browser editor.

Look for ``<body>`` tag and put your form code in a location that makes sense for your website. For example:

```html
		<div id="marketing">
			    <!-- Begin MailChimp Signup Form -->
<link href="//cdn-images.mailchimp.com/embedcode/slim-081711.css" rel="stylesheet" type="text/css">
<style type="text/css">
	#mc_embed_signup{background:#fff; clear:left; font:14px Helvetica,Arial,sans-serif; }
	/* Add your own MailChimp form style overrides in your site stylesheet or in this style block.
	   We recommend moving this block and the preceding CSS link to the HEAD of your HTML file. */
</style>
<div id="mc_embed_signup">
<form action="//getgymnast.us10.list-manage.com/subscribe/post?u=f84937ea3dcb3a0e8caee05e2&amp;id=9e0073bd48" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_blank" novalidate>
    <div id="mc_embed_signup_scroll">
	<label for="mce-EMAIL">Subscribe to our mailing list</label>
	<input type="email" value="" name="EMAIL" class="email" id="mce-EMAIL" placeholder="email address" required>
    <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->
    <div style="position: absolute; left: -5000px;"><input type="text" name="b_f84937ea3dcb3a0e8caee05e2_9e0073bd48" tabindex="-1" value=""></div>
    <div class="clear"><input type="submit" value="Subscribe" name="subscribe" id="mc-embedded-subscribe" class="button"></div>
    </div>
</form>
</div>
</div>
```

When you click ``Preview`` in in-browser editor, you will see the form appear in your landing page.

You can further customise the embedded form via ``css`` or in ``HTML`` by adding styles.

Once you are happy with result, click "Publish" and it will appear for all the visitors of you landing page.

## Google Analytics

*NOTE: You can use Google Analytics via our Segment integration by flipping a switch. Check [here](https://segment.com/docs/integrations/google-analytics) for more.*

Google Analytics is the most popular analytics tool for the web because it's free and supports a wide range of features. It's especially good at measuring traffic sources and ad campaigns.

### Get Google Analytics Tracking Code

Log in to your Google Analytics dashboard, follow "Admin" tab. Create a new property by entering your app name and url (f.e. "my-awesome-app" and "my-awesome-app.closeheatapp.com").

That will lead you to a page with your Tracking ID and Tracking code. Copy the tracking code that should look like this:

```html
<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

  ga('create', 'UA-43857026-11', 'auto');
  ga('send', 'pageview');

</script>
```

### Add tracking code to your closeheat landing page via in-browser editor

Make sure you are logged in closeheat and open your landing page (f.e. "http://my-awesome-app.closeheatapp.com").

Look in the lower right corner for closeheat logo and click it. Doing that will open an in-browser editor.

Look for ``</head>`` closing tag and put your tracking code right above it. For example:

```html
<head>
<title>My Awesome Website</title>
<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

  ga('create', 'UA-43857026-11', 'auto');
  ga('send', 'pageview');

</script>
</head>
```

Once the code is in place - click "Publish". After the publishing is done, Google Analytics will start sending statistics to your dashboard.

## Optimizely (A/B tests)

*NOTE: You can use Optimizely via our Segment integration by flipping a switch. Check [here](https://segment.com/docs/integrations/optimizely) for more.*

Optimizely is a dead-simple A/B testing tool that lets your marketing team test changes on your website in a WYSIWYG editor without having to write any code. Segment will pass events and traits to Optimizely, and send experiment variations to other tools.

### Get Optimizely script code

Create a new project on Optimizely and head over to "Settings" tab. Copy the code snippet that looks like this:

```html
<script src="//cdn.optimizely.com/js/2961540054.js"></script>
```

### Add Optimizely code to your closeheat landing page via in-browser editor

Make sure you are logged in closeheat and open your landing page (f.e. "http://my-awesome-app.closeheatapp.com").

Look in the lower right corner for closeheat logo and click it. Doing that will open an in-browser editor.

Look for ``<head>`` **opening** tag and put your tracking code right below it. For example:

```html
<head>
<script src="//cdn.optimizely.com/js/2961540054.js"></script>
<title>My Awesome Website</title>
</head>
```

Once the code is in place - click "Publish". After the publishing is done, Optimizely will be connected to your landing page.

### Set up an experiment

Head to "Overview" tab and click "New Experiment" and enter your landing page url (f.e. "http://my-awesome-app.closeheatapp.com").

Wait for the loading to happen and you should see your landing page successfully loaded.

Click on elements, edit them to create a new A/B experiment page. Once you're done - click "Save now" and "Start Experiment".

Wait for a few seconds for Optimizely to push their changes and visit your landing page (go to "http://my-awesome-app.closeheatapp.com").

You will see your experiment running.
