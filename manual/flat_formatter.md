The flat formatter does not report example groups. It only lists the examples 
executed and adds the failure reason YAML block for each failed example.
Configure the `--format` option to use this format:
```sh
--format RSpec::TAP::Formatters::Flat
```

The generated report for [String spec](string_spec.md):
```text
TAP version 13
not ok 1 - String#present? when nil returns false
  ---
  location: "./string_spec.rb:8"
  error: |-
    Failure/Error: expect(string.present?).to eq(false)
    NoMethodError:
      undefined method `present?' for nil:NilClass
  backtrace: "./string_spec.rb:9:in `block (4 levels) in <top (required)>'"
  ...
ok 2 - String#present? when whitespaces and other characters returns true
ok 3 - String#present? when whitespaces only returns false
ok 4 - String#blank? returns true # TODO: need to implement blank? for NilClass
not ok 5 - String#blank? returns false
  ---
  location: "./string_spec.rb:31"
  error: |-
    Got 2 failures from failure aggregation block:
      1) expected: true
              got: false
         (compared using ==)
         Diff:
         @@ -1,2 +1,2 @@
         -true
         +false
      2) expected: true
              got: false
         (compared using ==)
         Diff:
         @@ -1,2 +1,2 @@
         -true
         +false
  ...
ok 6 - String#squish squishes # SKIP: it is Ruby not Rails
1..6
# tests: 6, passed: 2, failed: 2, pending: 2
# duration: 0.034659 seconds
# seed: 35536
```
