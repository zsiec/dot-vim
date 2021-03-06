# ack.vim #

This plugin is a front for the Perl module
[App::Ack](http://search.cpan.org/~petdance/ack/ack).  Ack can be used as a
replacement for 99% of the uses of _grep_.  This plugin will allow you to run
ack from vim, and shows the results in a split window.


## Installation ##

You have to install [ack](http://search.cpan.org/~petdance/ack/ack), of course.  On Ubuntu, that's as easy as

<pre>
  <code>
  sudo apt-get install ack-grep
  </code>
</pre>

Otherwise, you are on your own.

As for the plugin:

The file ack.vim goes in ~/.vim/plugin, and the ack.txt file belongs in ~/.vim/doc.  Be sure to run

    :helptags ~/.vim/doc

or

    :helptags $VIMRUNTIME/doc

afterwards.


## Usage ##

    :Ack [options] {pattern} [{directory}]

Search recursively in {directory} (which defaults to the current directory) for the {pattern}.

Files containing the search term will be listed in the split window, along with
the line number of the occurrence, once for each occurrence.  [Enter] on a line
in this window will open the file, and place the cursor on the matching line.

Just like where you use :grep, :grepadd, :lgrep, and :lgrepadd, you can use
:Ack, :AckAdd, :LAck, and :LAckAdd respectively.

**From the [ack docs](http://search.cpan.org/~petdance/ack/ack)** (my favorite feature):

<pre>
  <code>
--type=TYPE, --type=noTYPE

    Specify the types of files to include or exclude from a search. TYPE is a filetype, like perl or xml. --type=perl can also be specified as --perl, and --type=noperl can be done as --noperl.

    If a file is of both type "foo" and "bar", specifying --foo and --nobar will exclude the file, because an exclusion takes precedence over an inclusion.

    Type specifications can be repeated and are ORed together.

    See ack --help=types for a list of valid types.
  </code>
</pre>

This Vim plugin is derived (and by derived, I mean copied, essentially) from
Antoine Imbert's blog post [Ack and Vim
Integration](http://blog.ant0ine.com/2007/03/ack_and_vim_integration.html) (in
particular, the function at the bottom of the post).  I added a help file that
provides just enough reference to get you going.  I also highly recommend you
check out the docs for the Perl script 'ack', for obvious reasons: [ack -
grep-like text finder](http://search.cpan.org/~petdance/ack/ack).


_I will not upload this to vim.org without ant0ine's permission.  I have
attempted to contact him, but I have not recieved a response.  Also, be aware
that if he asks me to remove this, I'll do so immediately.  Grab it while it's
hot!_
