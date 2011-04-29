
This repo contains several slide presentations for use during the Railsbridge Open Workshops (specifically the Ruby For Women Workshops).


# Installing Showoff

We use a Ruby app called `showoff` to generate and serve the workshop slides.

Alex has been improving showoff; until his latest patches get accepted and released, you will have to download and install his version, as follows:

    git clone git://github.com/alexch/showoff.git
    cd showoff
    bundle install
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

# Running several presentations in a row

This should be doable but for now it's not easy. (It depends on showoff allowing more than one `showoff.json` file in a single directory.)

# Editing slides

Slides are in [Markdown]() format. Showoff will read all `.md` files in alphabetical order.

You can also add custom `.css` and `.js` files, which will get imported into all slide sets.

Images should be in the current directory. If you want you can make a symlink to `../img` but that might not work on all OSs (i.e. Windows).

# Printing slides

Not well supported. Try

    showoff static

# Support

Email <mailto:railsbridge-workshops@googlegroups.com>

