# Jquery::Emojiarea::Rails

jquery.emojiarea.js plugin is wrapped with a gem for Rails asset pipeline.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'jquery-emojiarea-rails'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install jquery-emojiarea-rails

## Usage

`assets/javascripts/application.js` :

```javascript
...

// alternatively, jquery.emojiarea.min
//= require jquery.emojiarea    
//= require packs/basic/emojis
...

```

`assets/javascripts/emojiarea_init.coffee` ;

```coffee
$(document).on "turbolinks:load", ->
  $('.emojiarea').emojiarea
    wysiwyg: true
```


`assets/stylesheets/application.scss` :

```css

@import 'jquery.emojiarea';
@import 'emojiarea_init';

```

`_form.html.erb` :

```rb
<%= simple_form_for @message, remote: true do | f | %>
  <%= f.input :content, as: :text, label: false, input_html: { class: 'emojiarea', rows: 5 }  %>
  <%= f.submit class: 'btn btn-outline-primary' %>
<% end %>
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release` to create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

1. Fork it ( https://github.com/[my-github-username]/jquery-emojiarea-rails/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
