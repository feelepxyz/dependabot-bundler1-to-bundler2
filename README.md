# dependabot-bundler1-to-bundler2

This scenario currently works as expected in dependabot-core.

`Gemfile.lock` has been bundled with bundler 1.17.3, guard-bundler 2.2.1 is installed that requires bundler v1, but 3.0.0 requires bundler v2 so we should not propose an update.

Test this update in dependabot-core:

```
bin/dry-run.rb bundler dsp-testing/dependabot-bundler1-to-bundler2 --cache=files --dep=guard-bundler
```

Expected output:

```
=== guard-bundler (2.2.1)
 => checking for updates 1/1
 => latest available version is 3.0.0
 => latest allowed version is 2.2.1
 => requirements to unlock: update_not_possible
 => requirements update strategy: bump_versions
    (no update possible 🙅‍♀️)
 ```
