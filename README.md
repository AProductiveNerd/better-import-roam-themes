# better-import-roam-themes
When you are using Roam Research on your phone, you probably don't want to load whole CSS themes. Here is a roam/js snippet that allows you to only load CSS on bigger devices.

Just replace copy the code below and replace the url with the source URL of your CSS of choice!
Then paste the code in a javascript code block under a roam/js block and hit Yes, I know what I'm doing

```javascript
if (screen.width >= 500) {
  const url = "https://rcvd.github.io/roam-css-system/themes/apple_light.css";
  const element = document.createElement("link");
  element.setAttribute("rel", "stylesheet");
  element.setAttribute("type", "text/css");
  element.setAttribute("href", url);
  document.getElementsByTagName("head")[0].appendChild(element);
}```
