to_source
=========

[![Build Status](https://secure.travis-ci.org/mbj/to_source.png?branch=master)](http://travis-ci.org/mbj/to_source)
[![Dependency Status](https://gemnasium.com/mbj/to_source.png)](https://gemnasium.com/mbj/to_source)
[![Code Climate](https://codeclimate.com/github/mbj/to_source.png)](https://codeclimate.com/github/mbj/to_source)

Reverse parser to generate source code from the Rubinius AST. Also works well under MRI using the mutant-melbourne gem.
Currently only support for 1.9 mode!

To source is the backend of [mutant](https://github.com/mbj/mutant) it is used to create the (mutated) source that is 
evaled into the vm. Also for creating the diffs.

It should be able to create equivalent, but not identical, source. The current focus is to create *correct* but not 
*beautiful* source. Once correctnes is at 100% I'll focus on beautifullnes, so pls do not complain about excess of 
parantheses now ;).

Installation
------------

Install the gem ```to_source``` via your preferred method.

Examples
--------

```ruby
require 'to_source'
some_code = "a = 123"
ast = some_code.to_ast
# => #<Rubinius::AST::LocalVariableAssignment:0x21b8
#       @value=#<Rubinius::AST::FixnumLiteral:0x21bc @value=123 @line=1>
#       @variable=nil @line=1 @name=:a>
ast.to_source
# => "a = 123"
```

Credits
-------

* [Markus Schirp (mbj)](https://github.com/mbj), [@_m_b_j_](http://twitter.com/_m_b_j_) on twitter
* [Josep M. Bach (Txus)](http://txustice.me), [@txustice](http://twitter.com/txustice) on twitter


Contributing
-------------

* Fork the project.
* Make your feature addition or bug fix.
* Add tests for it. This is important so I don't break it in a
  future version unintentionally.
* Commit, do not mess with Rakefile or version
  (if you want to have your own version, that is fine but bump version in a commit by itself I can ignore when I pull)
* Send me a pull request. Bonus points for topic branches.

License
-------

See LICENSE
