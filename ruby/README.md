Style
=====

Formatting
----------

* Avoid inline comments.
* Delete trailing whitespace or configure your editor to do so.
* Don't include spaces after `(`, `[` or before `]`, `)`.
* If you break up an argument list, keep the arguments on their own lines and
  closing parenthesis on its own line.
* If you break up a hash, keep the elements on their own lines and closing curly
  brace on its own line.
* Indent continued lines two spaces.
* Indent private methods equal to public methods.
* Use 2 space indentation (no tabs).
* Use an empty line between methods.
* Use newlines around multi-line blocks.
* Use spaces around operators, after commas, after colons and semicolons, around
  `{` and before `}`.
* Use [Unix-style line endings] (`\n`).
* Use [uppercase for SQL key words and lowercase for SQL identifiers].

class SomeClass
  SOME_CONSTANT = 'upper case name'

  def initialize(attributes)
    @some_attribute = attributes[:some_attribute]
    @another_attribute = attributes[:another_attribute]
    @user_factory = attributes[:user_factory]
  end

  def method_with_arguments(argument_one, argument_two)
    this_is_a_really_long_line_that_should_be_broken_up_over_multiple_lines_and.
      every_line_but_the_first_is_indented
  end

  def method_with_multiline_block
    some_method_before_block(should_be_followed_by_a_newline)

    items.each do |item|
      do_something_with_item
    end

    some_method_after_block(should_follow_after_newline)
  end

  def method_with_single_line_block
    items.map { |item| item.some_attribute }
  end

  def method_that_returns_an_array
    [item_one, item_two]
  end

  def method_that_returns_a_hash
    { :key => 'value' }
  end

  def method_with_large_hash
    {
      :one => 'value',
      :two => 'value'
    }
  end

  def invoke_method_with_arguments_on_multiple_lines
    some_method(
      i_am_a_long_variable_name_that_i_will_never_fit_on_one_line_with_others,
      two,
      three
    )

    # Bad:
    some_method(one,
                two)
  end

  def method_that_uses_infix_operators
    left + middle - right
  end

  def method_without_arguments
    if complex_condition?
      positive_branch
    else
      negative_branch
    end

    rest_of_body
  end

  def method_that_uses_factory
    user = @user_factory.new
    user.ensure_authenticated!
  end

  def self.class_method
    method_body
  end

  private

  def complex_condition?
    part_one? && part_two?
  end
end


[uppercase for SQL key words and lowercase for SQL identifiers]: http://www.postgresql.org/docs/9.2/static/sql-syntax-lexical.html#SQL-SYNTAX-IDENTIFIERS
[Unix-style line endings]: http://unix.stackexchange.com/questions/23903/should-i-end-my-text-script-files-with-a-newline

Naming
------

* Avoid abbreviations.
* Avoid types in names (`user_array`).
* Name the enumeration parameter the singular of the collection.
* Name variables, methods, and classes to reveal intent.
* Treat acronyms as words in names (`XmlHttpRequest` not `XMLHTTPRequest`),
  even if the acronym is the entire name (`class Html` not `class HTML`).
* Name variables holding a factory with `_factory` (`user_factory`).
* Name variables created by a factory after the factory (`user_factory`
  creates `user`).

Organization
------------

* Order methods so that caller methods are earlier in the file than the methods
  they call.
* Order methods so that methods are as close as possible to other methods they
  call.

Sass
----
### Formatting
* Use the *Scss* syntax.
* Use hyphens when naming mixins, extends, classes, functions & variables: `span-columns` not `span_columns` or `spanColumns`.
* Use space between property and value: `width: 20px` not `width:20px`.
* Use a blank line above selector that has styles.
* Prefer hex color codes `#000`.
* Use `//` for comment blocks not `/* */`.
* Use a space between selector and `{`.
* Use single quotation marks for attribute selectors and property values.
* Use only lowercase, including colors.
* Don't add a unit specification after `0` values, unless required by a mixin.

### Order
* Use alphabetical order for declarations.
* Place @extends and @includes at the top of your declaration list.
* Place media queries directly after the declaration list.
* Place concatenated selectors second.
* Place pseudo states and elements third.
* Place nested selectors last.

### Selectors
* Don't use ID's for style.
* Use meaningful names: `$visual-grid-color` not `$color` or `$vslgrd-clr`.
* Use ID and class names that are as short as possible but as long as necessary.
* Append the prefix js- to ID's that are used by Javascript.
* Avoid using the direct descendant selector `>`.
* Avoid nesting more than 4 selectors deep.
* Don't nest more than 6 selectors deep.
* Use HTML tags on vague classes that need a qualifier like `header.application` not `.main`.
* Avoid using the HTML tag in the class name: `section.news` not `section.news-section`.
* Avoid using HTML tags on classes for generic markup `<div>`, `<span>`: `.widgets` not `div.widgets`.
* Avoid using HTML tags on classes with specific class names like `.featured-articles`.
* Avoid using comma delimited selectors.
* Avoid nesting within a media query.

### Organization
* Use Bourbon for a Sass Library.
* Use Neat for a grid framework.
* Use Bitters / Base folder for style on HTML tags, global variables, global extends and global mixins.
* Use Normalize as a browser reset.
* Use HTML structure for ordering of selectors. Don't just put styles at the bottom of the Sass file.
* Prefer the same file structure that is found in app/views.
* Avoid having files longer than 100 lines.

CoffeeScript
------------

* Initialize arrays using `[]`.
* Initialize empty objects and hashes using `{}`.
* Use `CamelCase` for classes, `lowerCamelCase` for variables and functions,
  `SCREAMING_SNAKE_CASE` for constants, `_single_leading_underscore` for
  private variables and functions.
* Prefer `is` to `== ` or `===`
* Prefer `or` and `and` to `||` and `&&`

Ruby
----

[Sample](samples/ruby.rb)

* Avoid conditional modifiers (lines that end with conditionals).
* Avoid multiple assignments per line (`one, two = 1, 2`).
* Avoid organizational comments (`# Validations`).
* Avoid ternary operators (`boolean ? true : false`). Use multi-line `if`
  instead to emphasize code branches.
* Avoid explicit return statements.
* Avoid using semicolons.
* Don't use `self` explicitly anywhere except class methods (`def self.method`)
  and assignments (`self.attribute =`).
* Prefer `detect` over `find`.
* Prefer `inject` over `reduce`.
* Prefer `map` over `collect`.
* Prefer `select` over `find_all`.
* Prefer single quotes for strings.
* Use `_` for unused block parameters.
* Use `%{}` for single-line strings needing interpolation and double-quotes.
* Use `&&` and `||` for Boolean expressions.
* Use `{...}` for single-line blocks. Use `do..end` for multi-line blocks.
* Use `?` suffix for predicate methods.
* Use `CamelCase` for classes and modules, `snake_case` for variables and
  methods, `SCREAMING_SNAKE_CASE` for constants.
* Use `def self.method`, not `def Class.method` or `class << self`.
* Use `def` with parentheses when there are arguments.
* Use `each`, not `for`, for iteration.
* Use heredocs for multi-line strings.

ERb
---

[Sample](samples/erb.rb)

* When wrapping long lines, keep the method name on the same line as the ERb
  interpolation operator and keep each method argument on its own line.
* Prefer double quotes for attributes.

HTML
----

* Prefer double quotes for attributes.

Rails
-----

* Avoid `member` and `collection` routes.
* Use private instead of protected when defining controller methods.
* Name date columns with `_on` suffixes.
* Name datetime columns with `_at` suffixes.
* Name initializers for their gem name.
* Order ActiveRecord associations alphabetically by attribute name.
* Order ActiveRecord validations alphabetically by attribute name.
* Order controller contents: filters, public methods, private methods.
* Order model contents: constants, macros, public methods, private methods.
* Put application-wide partials in the [`app/views/application`] directory.
* Use `def self.method`, not the `scope :method` DSL.
* Use the default `render 'partial'` syntax over `render partial: 'partial'`.

[`app/views/application`]: http://asciicasts.com/episodes/269-template-inheritance

Rails Routes
------------

* Avoid the `:except` option in routes.
* Order resourceful routes alphabetically by name.
* Use the `:only` option to explicitly state exposed routes.

Background Jobs
---------------

* Define a `PRIORITY` constant at the top of delayed job classes.
* Define two public methods: `self.enqueue` and `perform`.
* Put delayed job classes in `app/jobs`.

Email
-----

* Use one `ActionMailer` for the app. Name it `Mailer`.
* Use the user's name in the `From` header and email in the `Reply-To` when
  [delivering email on behalf of the app's users].

[delivering email on behalf of the app's users]: http://robots.thoughtbot.com/post/3215611590/recipe-delivering-email-on-behalf-of-users

Testing
-------

* Avoid the `private` keyword in specs.
* Order ActiveRecord association tests alphabetically by attribute name.
* Order ActiveRecord validation tests alphabetically by attribute name.
* Prefer `eq` to `==` in RSpec.
* Separate setup, exercise, verification, and teardown phases with newlines.
* Use RSpec's [`expect` syntax].
* Use `not_to` instead of `to_not` in RSpec expectations.

[`expect` syntax]: http://myronmars.to/n/dev-blog/2012/06/rspecs-new-expectation-syntax

#### Acceptance Tests

[Sample](samples/acceptance_test.rb)

* Avoid scenario titles that add no information, such as "successfully."
* Avoid scenario titles that repeat the feature title.
* Place helper methods for feature specs directly in a top-level `Features`
  module.
* Use Capybara's `feature/scenario` DSL.
* Use names like `ROLE_ACTION_spec.rb`, such as
  `user_changes_password_spec.rb`, for feature spec file names.
* Use only one `feature` block per feature spec file.
* Use scenario titles that describe the success and failure paths.
* Use spec/features directory to store feature specs.
* Use spec/support/features for support code related to feature specs.

#### Factories

* Order `factories.rb` contents: sequences, traits, factory definitions.
* Order factory attributes: implicit attributes, explicit attributes,
  child factory definitions. Each section's attributes are alphabetical.
* Order factory definitions alphabetically by factory name.
* Use one factories.rb file per project.

#### Unit Tests

[Sample](samples/testing.rb)

* Don't prefix `it` block descriptions with 'should'.
* Name outer `describe` blocks after the method under test. Use `.method`
  for class methods and `#method` for instance methods.
