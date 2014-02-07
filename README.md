# topcoat-xcss

A demo (and incomplete!) port of TopCoat to [xCSS][xcss].

The structure is the following:

    ├── README.md
    ├── lib                     <--- components
    │   ├── button-base.xcss
    │   ├── button.xcss
    │   └── utils.xcss
    ├── package.json
    ├── styles.xcss             <--- stylesheet
    └── themes                  <--- themes
        └── theme.js

To generate resulted CSS use `xcss` utility on `styles.xcss` which specifies how
which components to use and which theme to apply:

    @require "./themes/theme.js" as theme;  // bring theme module into scope
    @import "./lib/button.xcss" with theme; // import a comment and apply theme


    body {
      width: 12px;
    }

from command line:

    % npm install

    % ./node_modules/.bin/xcss ./styles.xcss > ./styles.css

[xcss]: https://github.com/andreypopp/xcss
