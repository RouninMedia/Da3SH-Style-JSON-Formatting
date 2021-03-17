# Da3SH Style JSON Formatting
When formatted using *Da3SH Style*, JSON displays with more vertical spacing and less horizontal spacing.

```
formatJSON(json) {

  let formattedJSON = JSON.stringify(JSON.parse(json), null, 2);
  formattedJSON = formattedJSON.replace(/[\,]\n([\s]*)/g, ',\n\n$1');
  formattedJSON = formattedJSON.replace(/([\[\{])\n([\s]*)/g, '$1\n\n$2');
  formattedJSON = formattedJSON.replace(/([\[\{])\n\s*(\n\s*)([\[\{])\n(\n\s*\")/g, '$1$2$3$4');
  formattedJSON = formattedJSON.replace(/(\:\s\[)\n(\s*\{)/g, '$1\n\n$2');

  return formattedJSON;
}

```
