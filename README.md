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
}
```

If you want to use in-graph css, you can use with the following. Just replace the value of the variable `css` with the css you want. Make sure to surround the css with backticks( ` )

```javascript
if (screen.width >= 500) {
  const css = `
    .rm-bq {
      /*   font-family: "Lobster", cursive !important; */
      font-size: 44px;
      line-height: 50px;
    }

    .rm-bq::before {
      content: "💡";
    }

    .easy {
        background-color: rgba(73, 131, 193, 0.64);
    }

    .meh {
        background-color: rgba(255, 255, 0, 0.35);
    }

    .hard {
        background-color: rgba(255, 0, 0, 0.35);
    }
  `;

  const element = document.createElement("style");
  element.setAttribute("type", "text/css");
  element.innerText = css;
  document.getElementsByTagName("head")[0].appendChild(element);
}
```
