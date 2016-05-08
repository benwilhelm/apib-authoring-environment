# API Blueprint Authoring Environment 

This a [Gulp][gulp] workflow for authoring API documentation in the .apib 
([API Blueprint][apib]) 
format. It allows the blueprint to be decomposed into smaller files for authoring, 
then concatenated into a single .apib file for parsing and documentation. The 
resulting file is used to generate HTML documentation for your API, as well as 
run a [Drakov][drakov] mock server to develop front end clients against.

[gulp]: http://gulpjs.com/
[apib]: https://apiblueprint.org/
[drakov]: https://www.npmjs.com/package/drakov

## Installation

For the moment, you'll either want to fork this repository or else clone it,
remove the .git directory, and re-initialize as a new git repo.  Eventually I'll 
probably make this a yeoman generator or something, but for now it's just a
little old git repo.

Once you have the base files, run `npm install` to get your dependencies.

## Usage 

Run `gulp` to start watching the source directories and serving the html
documentation and the mock server. Fill in your API description
in `api-src/_header.apib`, and begin documenting your routes in `api-src/routes`
directory, and optionally your data structures in `api-src/data-structures`. All 
`.apib` files in the `api-src` directory are concatenated, so you can split up 
your files however you please, as long as your sections are properly headed 
according to the [API Blueprint spec][apib-spec].

API docs are available at http://localhost:8080/api-blueprint.html 

Mock server is at http://localhost:8000. 

**Note:** The watch task does not recognize when new files are added, so as you 
add files in the `api-src` directory, you'll need to stop and restart the gulp 
task.

[apib-spec]: https://github.com/apiaryio/api-blueprint/blob/master/API%20Blueprint%20Specification.md
