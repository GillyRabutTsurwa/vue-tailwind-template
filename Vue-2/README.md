# Vue-Tailwind setup
- Install Vue & Tailwind (Obvo);
- Make a CSS folder (ideally in your assets folder) and add these three lines to add tailwind to your CSS: 
    ```
    @tailwind base;
    @tailwind components;
    @tailwind utilities;
    ```
- **Do not forget** to import your css file. You can do it either in your App.vue file (either in the CSS or the Javascript) or in your main.js file. I will do mine in my main.js file.
- Make a tailwind.config.js file on the root directory. On it you can customise and configure your tailwind. An example looks like [this](https://tailwindcss.com/docs/configuration/)
- Make a postcss.config.js file on the root and add this code:
```javascript
  module.exports = {
  plugins: [
    // ...
    require('tailwindcss'),
    require('autoprefixer'),
    // ...
  ]
}
```

## Purging Unused CSS
- Tailwind should work now, but it is rather large and there is much unused CSS. In order to get rid of all of that and include what you're only using, we need to install **@fullhuman/postcss-purgecss**. 
- Next, add this code to your postcss.config.js file
```javascript
  const purgecss = require('@fullhuman/postcss-purgecss')({

  // Specify the paths to all of the template files in your project
  content: [
    './src/**/*.html',
    './src/**/*.vue',
    // etc.
  ],

  // This is the function used to extract class names from your templates
  defaultExtractor: content => {
    // Capture as liberally as possible, including things like `h-(screen-1.5)`
    const broadMatches = content.match(/[^<>"'`\s]*[^<>"'`\s:]/g) || []

    // Capture classes within other delimiters like .block(class="w-1/2") in Pug
    const innerMatches = content.match(/[^<>"'`\s.()]*[^<>"'`\s.():]/g) || []

    return broadMatches.concat(innerMatches)
  }
})

module.exports = {
  plugins: [
    require('tailwindcss'),
    require('autoprefixer'),
    ...process.env.NODE_ENV === 'production'
      ? [purgecss]
      : []
  ]
}
```
- We added the purgecss function and adding a line to our previous code which will purge our css in production mode (Line 51).
- Test to see if Tailwind works.

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
