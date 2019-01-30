# Rubocop Settings
> RuboCop's development is moving at a very rapid pace and there are often backward-incompatible changes between minor releases (since we haven't reached version 1.0 yet). To prevent an unwanted RuboCop update you might want to use a conservative version locking in your `Gemfile`.

This repository is used as version control for team rubocop settings. Most recent customization for `rubocop.yml` is based off `rubocop v0.61.1`.

# Setup Rubocop
## Install Rubocop Gem
In the project's `Gemfile`, add this to the `development` and `test` group.

```ruby
group :development, :test do
  ...
  gem 'rubocop', '~> 0.61.1', require: false
end
```

Run the command in the terminal to install the gem for the project
```
bundle install
```

## Setup Rubocop Settings
Clone the repository in any directory
```
git clone https://github.com/gxaAlfie/Rubocop-Settings.git
```

Copy the Rubocop Configuration file to the home directory
```
cp ~/Path/To/Rubocop-Settings/.rubocop.yml ~/.rubocop.yml
```

# Usage
## How to Run
To run `rubocop` for current directory, type the following command in the terminal:

```sh
rubocop
```

To run `rubocop` for a specific file / path, type the following command in the terminal:
```sh
rubocop <some_file or some_file_path>

e.g.
rubocop app/controllers/
rubocop app/controllers/application_controller.rb
```

## Sample Output
```sh
$ rubocop app/controllers/application_controller.rb
Inspecting 1 file
C

Offenses:

app/controllers/application_controller.rb:8:3: C: Metrics/AbcSize: Assignment Branch Condition size for set_locale is too high. [15.39/15]
  def set_locale ...
  ^^^^^^^^^^^^^^
app/controllers/application_controller.rb:9:5: C: Style/ConditionalAssignment: Use the return of the conditional for variable assignment and comparison.
    if current_user.present? ...
    ^^^^^^^^^^^^^^^^^^^^^^^^
app/controllers/application_controller.rb:15:14: C: Performance/RegexpMatch: Use match? instead of match when MatchData is not used.
    locale = locale.match(/ja|en/) ? locale : I18n.default_locale
             ^^^^^^^^^^^^^^^^^^^^^

1 file inspected, 3 offenses detected
```
