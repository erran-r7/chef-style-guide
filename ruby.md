# Ruby Style Guide
Most of the Ruby style I'd discuss is already addressed in
[@bbatsov](https://github.com/bbatsov)'s [Ruby Style Guide](https://github.com/bbatsov/ruby-style-guide).

## Ruby Style for Chef
1. When accessing node attributes use Symbols. I'm a Rubyist, so it's mostly a preference, but if you're contributing
to cookbooks I've been driving under [@rapid7-cookbooks](https://github.com/rapid7-cookbooks), then you should do so
for uniformity. This isn't really debatable since you can use the `:'foo-bar'` syntax for Symbols with none alpha-num
characters or `:"foo_#{str}"` for interpolation in a Symbol.

## Chef Gotchas
Since Chef still installs Ruby 1.8 to run on some systems you'll sadly have to use 1.8.7 Ruby syntax in any code run
on the node. Make sure to use 1.9+ syntax anywhere else though! Note that while Ruby 2.0.0 is awesome, I can't ask
everyone to use it since it's still a newer release :disappointed:.

For Hashes that will be evaluated on a node:
```
{
  :symbol => 'string',
  :foo_bar => 'foo bar with underscore!',
  :'baz-qux' => 'baz qux with dash',
  :"number_#{rand}" => 'a interpolated symbol'
}
```

For Hashes written that are only ran on your workstation:
```
{
  symbol: 'string',
  foo_bar: 'foo bar with underscore!',
  :'baz-qux' => 'baz qux with dash',
  :"number_#{rand}" => 'a interpolated symbol'
}
```

