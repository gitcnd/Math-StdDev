# Math-StdDev
Math::StdDev - Pure-perl mean and variance computation supporting running/online calculation (Welford's algorithm)


# SYNOPSIS

    #!/usr/bin/perl -w
      
    use Math::StdDev;

    my $d = new Math::StdDev();
    $d->Update(2);
    $d->Update(3);
    print $d->mean() . "\t" . $d->sampleVariance();

or

    perl -MMath::StdDev -e '$d=new Math::StdDev; $d->Update(10**8+4, 10**8 + 7, 10**8 + 13, 10**8 + 16); print $d->mean() . "\n" . $d->sampleVariance() . "\n"'

# DESCRIPTION

This module impliments Welford's online algorithm (see https://en.wikipedia.org/wiki/Algorithms\_for\_calculating\_variance )
Maybe one day in future the two-pass algo could be included, along with Kahan compensated summation... so much math, so little time...

## EXPORT

None by default.

## Notes

## new

Usage is

    my $d = new Math::StdDev();
or
    my $d = new Math::StdDev(1,2,3,4);  # Add one or more samples, or a population, right from the start

## Update

Usage is

    my $d->Update(123);
or
    my $d->Update(@list_of_scalars);

# AUTHOR

This module was written by Chris Drake `cdrake@cpan.org`. 

# COPYRIGHT AND LICENSE

Copyright (c) 2019 Chris Drake. All rights reserved.

This library is free software; you can redistribute it and/or modify
it under the same terms as Perl itself, either Perl version 5.18.2 or,
at your option, any later version of Perl 5 you may have available.
