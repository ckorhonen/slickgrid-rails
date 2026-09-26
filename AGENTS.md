# Working on slickgrid-rails

`lib/slickgrid/` contains the Rails engine and JSON table helper;
`vendor/assets/` contains SlickGrid assets. `Gemfile` delegates dependencies to
the gemspec, which currently requires railties ~> 4.0 despite the older summary.
Use a compatible Ruby/Rails environment and `bundle install`.

There is no checked-in test suite or test/lint/typecheck task. For Ruby changes,
run `ruby -c <changed-ruby-files>` one file at a time and exercise table output
with a focused example or a disposable Rails fixture. Asset changes need a
browser/asset-pipeline check in a compatible host app.

`bundle exec rake build` is the Bundler gem packaging task. Never substitute
`rake slickgrid:update` for validation: it clones upstream master and replaces
vendored files. Vendor upgrades and gem publishing require explicit scope.

## Completing changes

Follow existing patterns and carry authorized work through the relevant checks,
repairing failures caused by the change. Choose routine implementation details
directly; ask only when missing information materially changes scope or outcome.
For documentation-only edits, check the diff, referenced paths, and command
accuracy rather than starting application runtimes. If a prerequisite blocks a
check, report the exact blocker and continue independent authorized work. Close
with changed paths, checks actually run and results, and remaining unverified
behavior; distinguish commands inspected from commands executed.
