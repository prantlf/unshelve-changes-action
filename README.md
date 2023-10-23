# Unshelve Changed Files

GitHub action for restoring modified files from cache, which were stored by [shelve-changes-action] in another job earlier.

## Usage

Restore the modified files from cache:

```yml
- uses: prantlf/unshelve-changes-action@v1
```

## Inputs

The following parameters can be specified using the `with` object:

### files

Type: `String`<br>

Files to be restored from the cache, separated by spaces. Mandatory.

### branches

Type: `String`<br>
Default: `'main master'`

Branches which this action should run for, which are used to publishing releases. Use whitespace for separating the branch names. If you want to use multiple lines in YAML, introduce them with ">-". If you want to allow all branches, set the value to "*".

### enable

Type: `Boolean`<br>
Default: `true`

Can be set to `false` to prevent this action from running. It's helpful in the pipeline, which will not continue releasing, but only building and testing, and that will be decided in the middle of a job execution.

### discard-shelf

Type: `Boolean`<br>
Default: `true`

Can be set to `false` to prevent automatic discarding of the shelved files from the cache.

## License

Copyright (C) 2023 Ferdinand Prantl

Licensed under the [MIT License].

[MIT License]: http://en.wikipedia.org/wiki/MIT_License
[shelve-changes-action]: https://github.com/prantlf/shelve-changes-action
