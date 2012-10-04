![Barsoom](http://barsoom.se/barsoom.png)

# Barsoom developer's handbook
## Styleguide

We aim towards a consistent and document style so we don't waste time arguing over unimportant things with one another, or with ourselves.

* [General](#general)
* [HTML](#html)
* [Ruby](#ruby)


### General

#### Avoid trailing whitespace.

It's good practice as a developer to show invisible characters, since they can be significant. But when you do, trailing whitespace left by others can be annoying.

So show it, and strip it.

Avoid significant trailing whitespace. Use `<br>` over Markdown's double-space, use quoted strings for the `"--  "` e-mail signature convention and so on.

---

### HTML

#### Prefer `-` to `_` in CSS classes, ids, data attributes.

``` css
<div class="foo-bar" id="baz-boink" data-foo-bar="wat">
```

Rails `dom_id` uses `_`. Twitter Bootstrap uses `-`. We can't be consistent with both.

Dashes also mean that it's easier to grep for CSS `first-name` vs Ruby `first_name`.

---

### Ruby

#### Prefer 1.9-style hashes.

Do `{ json: :style }` and not `{ :hash => :rockets }` when possible.


#### No empty lines when indentation level changes.

But always put empty lines around multiline blocks when the indent level doesn't change.
Avoid more than one empty line.

```ruby
class Foo
  def bar
  end

  def baz
  end
end
```

Don't do any of this:

```ruby
class Foo

  def bar
  end


  def baz
  end
  def waz
  end

end
```

### Ruby on Rails

#### Avoid `default_scope`.

It tends to cause confusing behavior.