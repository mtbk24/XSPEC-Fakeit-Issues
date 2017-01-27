# Fakeit Example

This Fakeit example in PyXspec shows how to trick XSPEC into producing a type-II file that holds 10,000 spectra for the 'n3' detector.  

Because the n3 detector is originally of type-I format, Fakeit defaults output to a type-I format file.  

You need to trick Fakeit by providing a spectral file of type-II format, which is what the 'lle' file is for. (the 'lle' file).  

The type-II format file should be listed as the first spectra in the AllData containier, meaning AllData(1) should be the 'lle' file, and AllData(2) should be the 'n3' file.

n3 is a GBM NaI detector onboard the Fermi Space Telescope.  These spectral and background files were prepared in the RMFIT program provided by the GBM team and are therefore of type-I format.  The response file is of type-II format, but the spectral file would need to be as well for Fakeit to work without tricking it.

lle is the LAT Low Energy detector onboard Fermi.  These spectral and background files were prepared in the GTBURST program provided by the LAT team within the Fermi Science Tools and are type-II format.

<br />
<br />
<br />
<br />
      
<p>  </p>

The Notebook in this example names the file 
    fakespec_n3_grbm+pow_-01-_L_ 
with the model name having a plus sign.  
This causes problems for Fakeit for some reason; causing it to ouput type-I format instead of type-II.

Change the '+' to '-' in the filename and a type-II file holding 10,000 spectra will be created, as desired.
<pre><code> fakespec_n3_grbm+pow_-01-_L_.fak </code></pre>
to 
<pre><code> fakespec_n3_grbm-pow_-01-_L_.fake </code></pre>

Spectral files are provided here as well as the files created by the program.
