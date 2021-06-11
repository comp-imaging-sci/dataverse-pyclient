# dataverse-pyclient
A collection of python scripts to automatically download large dataset for Dataverse

## Download a dataset

The `download_client.py` script allows to download a dataset from Dataverse.

The client takes three command line arguments:
 - `--server_url` is the url of the Dataverse repository (e.g. `https://dataverse.harvard.edu`)
 - `--doi` is the persistent id (DOI) of the dataset (e.g. `doi:10.7910/DVN/CUFVKE`)
 - `--pattern` is a Unix filename matching pattern to download selected files from a repository (e.g. `*` will download all files in the the dataset)

This script has been tested on Linux and MacOS

### Examples

As an example we consider the [`2D Acoustic Numerical Breast Phantoms and USCT Measurement Data`](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/CUFVKE) dataset (doi:10.7910/DVN/CUFVKE). Please note that this is a very large dataset (~1TB) so download with cautions!

- Download the full dataset (not reccomended!):
  
  `python -u download_client.py --doi doi:10.7910/DVN/CUFVKE`
  
- Download all files with a given extension (e.g. all `.mat` files):
  
  `python -u download_client.py --doi doi:10.7910/DVN/CUFVKE --pattern *.mat`
  
- Download as specific file (e.g. `read_data.m`):
  
  `python -u download_client.py --doi doi:10.7910/DVN/CUFVKE --pattern read_data.m`
