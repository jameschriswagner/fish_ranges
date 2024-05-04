# fish_ranges
This is a project intended to assess the utility of presence/absence bottom trawl surveys of marine fish species in North America and Europe.
All fish range data obtained from https://www.aquamaps.org/.
MEOW shapefiles obtained from https://www.marineregions.org/.


true_range_limits.ipynb

    This code uses estimated fish range limits and checks them against existing Aquamaps' contemporary range estimates.
    Once ECDFs running south-north of each fish density map are generated, they are checked against those estimates,
    using the percentile of the Aquamaps distribution at which the latutude estimate falls as the main indicator of performance.

coastal_ecdfs-true-ranges.ipynb

    This code executes a similar process as true_range_limits.ipynb, with the exception that each ECDF is generated with
    respect to a specific coastline, and surveys are only evaluated with respect to subsets of aquamaps density
    maps that fall on the matching coast. Within this file, coastlines are defined using MEOW.

coastal_ecdfs-all-ranges.ipynb

    This is directly analogous to coastal_ecdfs-true-ranges.ipynb, with the exception being that leading and trailing
    edges are manually determined using the maximum and minimum range estimate across all surveys tracking each
    individual fish species, again on a specific coastline where that survey actually occurs.

coastal_ecdfs-SURVEY-RANGE.ipynb

    This file does exactly the same thing as coastal_ecdfs-all-ranges.ipynb, with the exception being how we define
    each coastal region. In this file, we define the coastal regions as being the intersection between the published
    survey ranges as outlined in the shapefile available at
    https://github.com/AquaAuma/TrawlSurveyMetadata/archive/refs/heads/master.zip, and the hand-selected coastal regions
    as generated and visualized by coastal_ecdfs-all-ranges.ipynb.
