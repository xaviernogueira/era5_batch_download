## era5_batch_download.py - A script to batch download ERA5 data iteratively

Inputs begin on line 372. An example of inputs, as well as information to assist set up is provided below.

#### Non-default Python prerequites: 
* iso3166
* cdsapi

------------------------------------------------------------------------------
### **Example inputs**

d_url = r'THE URL PATH OF THE DATASET YOU WANT TO DOWNLOAD ON CDS WEBSITE'

out_dir = r'A DIRECTORY PATH WHERE YOU WANT TO STORE DOWNLOADED FILES'

variables = ['VALID', 'VARIABLE', 'NAMES']

years = [2010, 2015, 2020]

form = 'netcdf' OR 'grib'

### Time parameters and area of interest inputs
months = # can be a list of month numbers, or 'ALL'

hours = # can be a list of hour numbers (military time), or 'ALL'

days = # can be a list of day of the month numbers, or 'ALL'

area = 'Germany' # SET TO None for Global coverage  # can be a place name (string), if None data is downloaded globally.


### Loop settings
LOOP_VARS = True # if true, each variable is output separately.

LOOP_DAYS = True # if True, a file is downloaded for the selected hours within each day (for hourly data only).

LOOP_MONTHS = False # if True, a file is downloaded for each month (for monthly data only)

------------------------------------------------------------------------------

## NOTE! The user must provide a  USER and API key %USERPROFILE%\.cdsapirc file 
1. Make a user account on https://cds.climate.copernicus.eu/.
1. Find your USER and API key @ https://cds.climate.copernicus.eu/user after logging in.
2. Make a cdsapirc.txt file and rename it to .cdsapirc. This file should be as shown in https://github.com/ecmwf/cdsapi README.
  * If having issues with this step, follow the advice here https://tinyurl.com/troubleshoot202.
3. Copy and paste the text in the black box from here https://cds.climate.copernicus.eu/api-how-to into the cdsapirc file and save (may need to use a Notebook+ or other advanced text editor).

### Once inputs are in place you can run the script!

Check active API requests @ https://cds.climate.copernicus.eu/cdsapp#!/yourrequests.

Information tracking the outputs are saved to a logging file 'era5_batch_download.log'
