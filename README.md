# Vital

A minimally invasive CSS framework for modern web applications.

- Vital is a reverse approach to "everything and the kitchen sink" CSS frameworks.
- Built with Sass and Slim for readability and maintainability.
- No ridiculous amounts of classes or nesting. No excessively buried code.
- Written almost entirely in em values, allowing for easy and consistent scaling.
- Small:

|                | Size  | Gzipped |
|:---------------|:------|:--------|
| CSS Framework  | 22 KB | 6 KB    |
| Icons (.svg)   | 3 KB  | 1 KB    |
| Icons (.eot)   | 2 KB  |         |
| Icons (.ttf)   | 2 KB  |         |
| Icons (.woff)  | 2 KB  |         |
| Javascripts    | 0     |         |
| Total          | 31 KB |         |


## Usage

A couple installation options are available:

- Download the latest release tarball from https://github.com/doximity/vital/releases.
- Install the `vital` Ruby Gem on your project.
- Use a precompiled release from RawGit.

Check out [our docs](http://vitalcss.com/get-started/) for information on installation methods, framework contents, templates, examples and more.

## Development

**NOTE**: The project requires Ruby 2.0+ for building its assets and documentation.

Initial setup:

```sh
git clone https://github.com/doximity/vital.git
cd vital
bundle

# If you want to build / work on documentation
cd docs
bundle
```

### Compiling assets locally

```sh
cd vital
bundle exec rake vital:build
```

### Compiling Font Icons

To compile font icons, you must first install FontForge.

```bash
# On Mac
# Requires Ruby 1.9.2+, FontForge with Python scripting
brew install fontforge --with-python
brew install eot-utils
```

After installation is complete, run `rake vital:compile_font`.

### Build the documentation

Vital is built using a simple static generator: https://middlemanapp.com/

```sh
cd vital/docs
bundle
bundle exec middleman
```

## Releasing a new version

- Ensure docs, `README.md`, `CHANGELOG.md` are up to date
- Bump version on `lib/vital/version.rb`
- `bundle exec rake vital:build`
- `git add ...` all of the updated files
- `git commit -m 'vX.Y.Z'`
- `git push origin master`
- `bundle exec rake release` to push to RubyGems
- `cd docs && bundle exec rake publish` to update GitHub pages
- Go to https://github.com/doximity/vital/releases and create a new release with the tarball attached
- Visit http://vitalcss.com/ and ensure it has been updated

## Reporting Issues and Suggestions

Please submit GitHub issues for problems with the library. Also, feel free to submit a pull-request with suggested changes.
