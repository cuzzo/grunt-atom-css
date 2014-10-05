# Grunt ATOM CSS

A Grunt task to compile your [ATOM CSS](https://github.com/cuzzo/atom "ATOM CSS").

# Usage

Grunt ATOM CSS allows you to easily compile your ATOM CSS for production. It works with Grunt, and is easily integrated with grunt-watch.

# Installation

```bash
npm install grunt-atom-css
```

# Configuration

Example Gruntfile:

```javascript
module.exports = function(grunt) {
  grunt.initConfig({ 
    atom: {
      options: {
        molecule_path: "example",
        molecular_rules_path: "example/molecular-rules.js",
        split_molecules_path: "example/sass/split-molecules.scss",
        sass_import_path: "example/sass/_imports.scss"
      }
    },

    watch: {
      react: {
        files: ["example/jsx/**/*.jsx"],
        tasks: ["react"]
      },
      sass: {
        files: ["example/sass/**/*.scss"],
        tasks: ["sass"]
      },
      atom: {
        files: ["example/**/*.atom"],
        tasks: ["atom"]
      }
    }
  });

  grunt.loadNpmTasks("grunt-contrib-watch");
  grunt.loadNpmTasks("grunt-atom-css");
});
```

Then you can just run `grunt atom` to compile all your ATOM CSS files. Alternatively, you can run `grunt watch` to compile all your ATOM CSS files any time you modify one of them.

# Options

* `molecule_path` - The path where your .atom files are stored.
* `molecular_rules_path` - The path at which to generate an imbeddable JavaScript Molecular Rules dictionary--the table that stores the CSS atoms that compose each of your CSS molecules.
* `split_molecules_path` - The path at which to generate the SASS file for CSS pseudo-class rules.
* `sass_import_path` - The SASS dependencies for psuedo-class rules.

# Resources

* [ATOM](https://github.com/cuzzo/atom-css "ATOM CSS") - The ATOM CSS specification.

# License

Grunt ATOM CSS is free--as in BSD. Hack your heart out, hackers.
