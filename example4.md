!SLIDE
# <em style="color:blue;">define request handling</em> : Request comes in, where do I send it #

    @@@ ruby
    # now deal with the various Methods we support.  
    # GET and HEAD do the lookup and such as normal
    if ( req.request == "GET" || req.request == "HEAD" ) {
      lookup; # do cache lookup return from there if possible
    } else if ( req.request == "PUT" ) {
       pass;
    } else {
       error 405 "Only GET, HEAD, PUT are supported.";
    }
