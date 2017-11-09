news-widget
===========

A widget to display BlockExplorer news.

## Usage

An example is below on how to use the BlockExplorer news widget:

```
<div id="myid"></div>
<script type="text/javascript" src="https://widget.blockexplorer.com/blockexplorer-news-widget.min.js"></script>
<script type="text/javascript">
function onReady(fn) {
  if (document.attachEvent ? document.readyState === "complete" : document.readyState !== "loading") {
    fn();
  } else {
    document.addEventListener('DOMContentLoaded', fn);
  }
};

onReady(function() {
  new BxpNewsWidget(document.getElementById("myid"));
});
</script>
```

You don't need to use onReady if you already are using a framework or code that does it, such as jQuery's $(function() {...}).

### Options

You can configure news-widget using data attributes on the element.

Example:

```
<div id="blockexplorer-news-widget" data-items="3" data-style="dark"></div>
```

or on the BxpNewsWidget class:

```
new BxpNewsWidget(el, options);
```

## Available options

| HTML Option | JS Option |Type | Default | Description |
|-------------|-----------|-----|---------|-------------|
|items|items|Integer|4|How many news items are displayed before scrolling|
|theme|theme|String|"light"|The theme of the widget. Set to "none" to display all CSS (so you can customize it yourself).|
|link-target|linkTarget|String|""|Where to open the linked item: _blank, _self, _parent, _top, framename|
|autoscroll|autoscroll|Boolean|true|Sets whether the content should autoscroll|
|autoscroll-interval|autoscrollInterval|Integer|6000|The amount of time between autoscrolling (in miliseconds)|
|autoscroll-duration|autoscrollDuration|Integer|1000|The amount of time it takes to scroll from one item to the next (in milliseconds)|
|autoscroll-interaction-pause-duration|autoscrollInteractionPauseDuration|Integer|3000|The amount of time to pause scrolling after the mouse leaves from hovering, or in the case of mobile when the user swipes/scrolls (in milliseconds)|
||on|Object|{}|Events to configure on initialization. E.g. on: {"eventname": fn}|

## Available events
|Name|Data|Description|
|----|----|-----------|
|beforeupdate||Called just before an update is started|
|update||Called after an update has been completed and the results rendered|
