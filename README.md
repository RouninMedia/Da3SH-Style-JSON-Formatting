# DaNIS3H Style JSON Formatting
When formatted using *DaNIS3H Style*, JSON displays with more vertical spacing and less horizontal spacing.

_______

## Invoking the `danis3hFormat()` Function
The `danis3hFormat()` function takes a single parameter - the `json` to be formatted:

    danis3hFormat('[{"element":"h1","classList":["mainHeading"],"elementChildren":[{"plainText":"Main Heading"}]}]');

_______

## The `danis3hFormat()` Function

```
danis3hFormat(json) {

  let formattedJSON = JSON.stringify(JSON.parse(json), null, 2);
  formattedJSON = formattedJSON.replace(/[\,]\n([\s]*)/g, ',\n\n$1');
  formattedJSON = formattedJSON.replace(/([\[\{])\n([\s]*)/g, '$1\n\n$2');
  formattedJSON = formattedJSON.replace(/([\[\{])\n\s*(\n\s*)([\[\{])\n(\n\s*\")/g, '$1$2$3$4');
  formattedJSON = formattedJSON.replace(/(\:\s\[)\n(\s*\{)/g, '$1\n\n$2');

  return formattedJSON;
}

```
