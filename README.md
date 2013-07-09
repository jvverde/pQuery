# NAME

Data::pQuery - a xpath like processor for json like data-objects (hashes and arrays)! 
It looks for data-objects which match the pQuery expression and returns a list
with matched data-objects  

# VERSION

Version 0.02

# SYNOPSIS

How to use it.

	use Data::pQuery;

	($\,$,) = ("\n",",");
	my $query = Data::pQuery->compile('a.*');
	my $data = {a => { b => 'bb', c => 'cc'}, aa => 'aa'};
	my $results = $query->process($data);
	my @values = $results->getvalues();
	print @values;                          #outputs 'bb,cc'
	my @refs = $results->getrefs();
	${$refs[0]} = 'new value';
	print $data->{a}->{b};                  #outputs 'new value'





# Data::pQuery methods



## new(pQuery)
Used only internally!!! Do nothing;

## compile(pQueryString)
Receives a pQuery string compile it and return a Data::pQuery::Processor object

## process(dataRef)
Receives a hash or array reference and return a Data::pQuery::Compiler object. 



# Data::pQuery::Processor methods

## new
Used only internally!!!

## process(data)
Query data and returns a Data::pQuery::util object



# Data::pQuery::Compiler methods

## new
Used only internally!!!

## compile(pQueryString)
Compile a pQuery string, query data and returns a Data::pQuery::util object



# Data::pQuery::util methods

## getrefs()
Returns a list o references for each matched data-object;

## getvalues()
Returns a list of values for each matched data-object;

# AUTHOR

Isidro Vila Verde, `<jvverde at gmail.com>`

# BUGS

Please report any bugs or feature requests to `bug-data-pquery at rt.cpan.org`, or through
the web interface at [http://rt.cpan.org/NoAuth/ReportBug.html?Queue=Data-pQuery](http://rt.cpan.org/NoAuth/ReportBug.html?Queue=Data-pQuery).  I will be notified, and then you'll
automatically be notified of progress on your bug as I make changes.



# SUPPORT

You can find documentation for this module with the perldoc command.

    perldoc Data::pQuery



You can also look for information at:

- RT: CPAN's request tracker (report bugs here)

    [http://rt.cpan.org/NoAuth/Bugs.html?Dist=Data-pQuery](http://rt.cpan.org/NoAuth/Bugs.html?Dist=Data-pQuery)

- AnnoCPAN: Annotated CPAN documentation

    [http://annocpan.org/dist/Data-pQuery](http://annocpan.org/dist/Data-pQuery)

- CPAN Ratings

    [http://cpanratings.perl.org/d/Data-pQuery](http://cpanratings.perl.org/d/Data-pQuery)

- Search CPAN

    [http://search.cpan.org/dist/Data-pQuery/](http://search.cpan.org/dist/Data-pQuery/)



# ACKNOWLEDGEMENTS



# LICENSE AND COPYRIGHT

Copyright 2013 Isidro Vila Verde.

This program is free software; you can redistribute it and/or modify it
under the terms of the the Artistic License (2.0). You may obtain a
copy of the full license at:

[http://www.perlfoundation.org/artistic\_license\_2\_0](http://www.perlfoundation.org/artistic\_license\_2\_0)

Any use, modification, and distribution of the Standard or Modified
Versions is governed by this Artistic License. By using, modifying or
distributing the Package, you accept this license. Do not use, modify,
or distribute the Package, if you do not accept this license.

If your Modified Version has been derived from a Modified Version made
by someone other than you, you are nevertheless required to ensure that
your Modified Version complies with the requirements of this license.

This license does not grant you the right to use any trademark, service
mark, tradename, or logo of the Copyright Holder.

This license includes the non-exclusive, worldwide, free-of-charge
patent license to make, have made, use, offer to sell, sell, import and
otherwise transfer the Package with respect to any patent claims
licensable by the Copyright Holder that are necessarily infringed by the
Package. If you institute patent litigation (including a cross-claim or
counterclaim) against any party alleging that the Package constitutes
direct or contributory patent infringement, then this Artistic License
to you shall terminate on the date that such litigation is filed.

Disclaimer of Warranty: THE PACKAGE IS PROVIDED BY THE COPYRIGHT HOLDER
AND CONTRIBUTORS "AS IS' AND WITHOUT ANY EXPRESS OR IMPLIED WARRANTIES.
THE IMPLIED WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR
PURPOSE, OR NON-INFRINGEMENT ARE DISCLAIMED TO THE EXTENT PERMITTED BY
YOUR LOCAL LAW. UNLESS REQUIRED BY LAW, NO COPYRIGHT HOLDER OR
CONTRIBUTOR WILL BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, OR
CONSEQUENTIAL DAMAGES ARISING IN ANY WAY OUT OF THE USE OF THE PACKAGE,
EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

