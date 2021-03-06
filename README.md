# NAME

WWW::ORCID - Module to interface with the ORCID webservice

# SYNOPSIS

    use WWW::ORCID;

    my $orcid   = WWW::ORCID::API::Pub->new;
    my $id      = '0000-0001-8390-6171';

    my $profile = $orcid->get_profile($id);
    my $bio     = $orcid->get_bio($id);
    my $works   = $orcid->get_works($id);

    my $result  = $orcid->search_bio({q => "johnson"});

    # Fielded search
    ############################################################
    # Fields
    #   - orcid
    #   - given-names
    #   - family-name
    #   - credit-name
    #   - other-names
    #   - email
    #   - external-id-reference
    #   - digital-object-ids
    #   - work-titles
    #   - keywords
    #   - creation date
    #   - last modified date
    #   - text
    # The query string follow the Lucene query syntax
    # See also: http://members.orcid.org/api/tutorial-searching-api-12-and-earlier
    my $result  = $orcid->search_bio({q => "family-name:johnson"});

    my $found   = $result->{'orcid-search-results'}->{'num-found'};

    # paging search results

    my $result2 = $orcid->search_bio({q => "family-name:hochstenbach", start => 10, rows => 10});

# DESCRIPTION

Module to interface with the ORCID webservice.

# VERSION

Version 0.0101

# SEE ALSO

[http://members.orcid.org/api](http://members.orcid.org/api)

# AUTHOR

Patrick Hochstenbach `<patrick.hochstenbach at ugent.be>`

Nicolas Steenlant, `<nicolas.steenlant at ugent.be>`

Simeon Warner `<simeon.warner at cornell.edu>`

# LICENSE AND COPYRIGHT

This program is free software; you can redistribute it and/or modify it
under the terms of either: the GNU General Public License as published
by the Free Software Foundation; or the Artistic License.

See http://dev.perl.org/licenses/ for more information.
