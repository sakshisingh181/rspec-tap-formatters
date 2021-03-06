The default formatter reports example groups with proper indentation and adds 
failure reason YAML blocks for each failed example. Configure the `--format`
option to use this format:
```sh
--format RSpec::TAP::Formatters::Default
```

The generated report for [String spec](string_spec.md):
```text
TAP version 13
# test: String {
  # group: #present? {
    # group: when whitespaces and other characters {
      ok 1 - returns true
      1..1
      # tests: 1, passed: 1
    }
    # group: when whitespaces only {
      ok 1 - returns false
      1..1
      # tests: 1, passed: 1
    }
    # group: when nil {
      not ok 1 - returns false
        ---
        location: "./string_spec.rb:8"
        error: |-
          Failure/Error: expect(string.present?).to eq(false)
          NoMethodError:
            undefined method `present?' for nil:NilClass
        backtrace: "./string_spec.rb:9:in `block (4 levels) in <top (required)>'"
        ...
      1..1
      # tests: 1, failed: 1
    }
    1..3
    # tests: 3, passed: 2, failed: 1
  }
  # group: #blank? {
    ok 1 - returns true # TODO: need to implement blank? for NilClass
    not ok 2 - returns false
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
    1..2
    # tests: 2, failed: 1, pending: 1
  }
  # group: #squish {
    ok 1 - squishes # SKIP: it is Ruby not Rails
    1..1
    # tests: 1, pending: 1
  }
  1..6
  # tests: 6, passed: 2, failed: 2, pending: 2
}
1..6
# tests: 6, passed: 2, failed: 2, pending: 2
# duration: 0.042018 seconds
# seed: 1334
```
