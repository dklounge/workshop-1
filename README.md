
This repo contains several slide presentations for use during the Railsbridge Open Workshops (specifically the Ruby For Women Workshops).

Not all presentations are ready to be shown yet!

# Installing Showoff

We use a Ruby app called `showoff` to generate and serve the workshop slides.

Alex has been improving showoff; until his latest patches get accepted and released, you will have to download and install his version, as follows:

    git clone git://github.com/alexch/showoff.git
    cd showoff
    bundle install --without optional
    rake gem:install

# Installing these slides

Alex has been working on these slides on a fork, so until they are accepted into the Railsbridge github repo, do this:

    git clone git://github.com/alexch/workshop.git

# Running a single presentation

For example, if you want to run the "Teacher Training" presentation, which lives in the `teachers` directory, do
    
    showoff serve teachers

This will launch a local Sinatra server on port 9090. Open your browser to `localhost:9090`. On a Mac you can run:

    open http://localhost:9090

Use arrow keys to navigate slides. Press '?' to see a help window.

(You can also `cd` into the directory and then run `showoff serve` if you like.)

# Running several presentations in a row

You can create a custom presentation out of any combination and ordering of the section directories by creating your own `showoff.json` file. See `nyc.json` for an example -- it's the same as the standard `showoff.json` but inserts NY-specific resources after the Welcome section.

# Editing slides

Slides are in [Markdown](http://daringfireball.net/projects/markdown/syntax) format. Showoff will read all `.md` files in alphabetical order.

You can also add custom `.css` and `.js` files, which will get imported into all slide sections.

Images should be in, or relative to, the current directory. If you want you can make a symlink to `../img` but that might not work on all OSs (i.e. Windows).

# Printing slides

Not well supported. Try

    showoff static

but be prepared to be disappointed. Same with PDFs.

# Support

Email <mailto:railsbridge-workshops@googlegroups.com>

# LICENSE

This project is under an open source license. We're not sure exactly which one... probably MIT.

Gill Sans is under copyright. It's a great slide font and it comes with all recent Macs (and Gill Sans MT comes with MS Office). But it might not be on the instructor's machine so I checked in a zip file. This was probably the wrong thing to do.

Here is Gill Sans licensing info
  http://www.fontslive.com/font/gill-sans-family.aspx
  http://www.ascendercorp.com/font/gill-sans/

"The Gill Sans stack should work on most all computers. Gill Sans comes on all
Macs and Gill Sans MT is installed with Microsoft Office, and Calibri (which
is a good stand-in for Gill Sans) is one the core Vista fonts and is installed
with both Office Windows and Office Mac. And lastly, if all else fails, use
Trebuchet" - http://www.artsiteframework.com/guide/fontstacks.php -- the stack
he's talking about is

  "Gill Sans", "Gill Sans MT", GillSans, Calibri, "Trebuchet MS", sans-serif

Perhaps we should replace it with a free font like SansBetween
  http://manfred-klein.ina-mar.com/
  http://manfred-klein.ina-mar.com/fonts/2008-02/SansBetween-MAC.zip
  http://manfred-klein.ina-mar.com/fonts/2008-02/SansBetween-PC.zip
