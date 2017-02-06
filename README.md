# Fakeit Example  
### XSPEC Version: 12.9.0k and PyXspec version: 1.1.0

This Fakeit example in PyXspec shows how to trick XSPEC into producing a type-II file that holds 10,000 spectra for the 'n3' detector.  

Because the n3 detector is originally of type-I format, Fakeit defaults output to a type-I format file.  

You need to trick Fakeit by providing a spectral file of type-II format, which is what the 'lle' file is for.  

Fakeit default setting are to use Poisson fluctuations for both the source and background, unless it detects a STAT_ERR column in the file.  If a STAT_ERR column is detected, Gaussian fluctuations are then applied.  If the file has both a STAT_ERR column and POISSERR = T in the header of the table holding the data, then POISSERR = T overrides the STAT_ERR column and Poisson fluctuations are applied.
*** If you need XSPEC to apply Gaussian fluctuations to the source, you MUST load that spectra into XSPEC before performing Fakeit.  If not, you only need to load the 'dummy file' and then pass the names of the response and background filenames to the Fakeit settings.  An output fileName needs to be supplied as well.

*** Fakeit_example_1 file:
This example is for if you don't need XSPEC to read the header or STAT_ERR column from the spectral file.  You only need to load the dummy file and pass settings for the spectral file.  The type-II format file is the only one that needs to be loaded into the AllData container, meaning AllData(1) should be the 'lle' file.  The 'n3' file, that we wish to make 10,000 synthetic spectra of, does not need to be loaded.  We only need to give the Fakeit Settings the filename, response filename, and background filename.  If the exposure is not in the background file's header, an exposure will need to be supplied to the settings as well.  fs2.exposure = 62

*** Fakeit_example_2 file:
When you need XSPEC to read the STAT_ERR or POISSERR = F from the source file, you will need to load it into XSPEC before running Fakeit.  See this example.

n3 is a GBM NaI detector onboard the Fermi Space Telescope.  These spectral and background files were prepared in the RMFIT program provided by the GBM team and are therefore of type-I format.  

lle is the LAT Low Energy detector onboard Fermi.  These spectral and background files were prepared in the GTBURST program provided by the LAT team within the Fermi Science Tools and are type-II format.

<br />
<br />
<br />
