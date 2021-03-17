# Da3SH Style JSON Formatting
When formatted using *Da3SH Style*, JSON displays with more vertical spacing and less horizontal spacing.

_______

## Invoking the `da3shFormat()` Function
The `da3shFormat()` function takes a single parameter - the `json` to be formatted:

    da3shFormat('[{"element":"h1","classList":["mainHeading"],"elementChildren":[{"plainText":"Main Heading"}]}]');

_______

## The `da3shFormat()` Function

```
da3shFormat(json) {

  let formattedJSON = JSON.stringify(JSON.parse(json), null, 2);
  formattedJSON = formattedJSON.replace(/[\,]\n([\s]*)/g, ',\n\n$1');
  formattedJSON = formattedJSON.replace(/([\[\{])\n([\s]*)/g, '$1\n\n$2');
  formattedJSON = formattedJSON.replace(/([\[\{])\n\s*(\n\s*)([\[\{])\n(\n\s*\")/g, '$1$2$3$4');
  formattedJSON = formattedJSON.replace(/(\:\s\[)\n(\s*\{)/g, '$1\n\n$2');

  return formattedJSON;
}

```
