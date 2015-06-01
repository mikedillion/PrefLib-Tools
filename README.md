# PrefLib-Tools
README.txt for PrefLib utilities (c) Nicholas Mattei and NICTA.

A a small of lightweight tools in Python3 for working with data from www.PrefLib.org and generating synthetic data for use in voting and preference experiments.

Please see www.PrefLib.org for more information about our project and a large library of real-world preference data For questions or comments please contact nsmattei@gmail.com or Nicholas.Mattei@nicta.com.au.

This code comes without warranty. Please use or distribute for research and academic uses only. Please use according to the citation and fair use requests on found at www.preflib.org.

# Release Version 0.2

This release includes the following 3 files:

1. GenerateProfiles.py
2. PreflibUtils.py
3. DomainRestriction.py

## OVERVIEW

The code in this release consists of the working versions of code that has
been used in my research for a couple of years.

Currently the code-base has the ability to:

- Read and write all the PrefLib file formats.

- Generate profiles according to various distributions including
	Impartial Culture (IC), Impartial Anonymous Culture (IAC), 
	Urn Cultures (UC), Single Peaked Impartial Culture (SPIC),
	and Mallows Mixture Models (MMM).  Please refer to
	GenerateProfiles.py for examples and an easy to use command line interface

- Test for domain restrictions like SinglePeakedness.

## DETAILS

The code is built around the following basic data objects.  These are all 
just basic Python data structures (lists and dictionaries).  The plan is to port this whole structure into a more OO friendly structure in the future when we finish the Matching toolkits.

Generally speaking a Profile (set of votes) is represented by one or more of the following elements.  votemap and rankmaps are two different ways to view the same profile and this should likely all be formalized under a "Profile" object in a future release.

- candmap
	-- A candmap is a dictionary that maps a candidate number onto a
	candidate name.

- votemap
	-- A votemap is a dictionary that maps a string representing
	a vote in PrefLib format onto the count of that vote in the 
	profile represented by the votemap.

- rankmap
	-- A rankmap is a dictionary that maps the candidate numbers
	to a rank (1 up to the number of candidates).  This 
	allows us to represent partial and strict orders in 
	the same way.

- rankmapcounts
	-- A rankmapcouns array is a parallel array to an array of rankmaps
	which keeps a count of the number of times that rankmap exists
	in a profile.




