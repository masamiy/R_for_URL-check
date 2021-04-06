# R_for_URL-check
This repository is to share R project to check many URLs by chunk

Original source: https://stackoverflow.com/questions/52911812/check-if-url-exists-in-r
Heaps of help from @joelnitta (https://github.com/joelnitta)

This takes a CSV file as input and checks the status of URLs in chunks in parallel.

To run this R script, it has to have 5 folders:
data: You need to place an original CSV file.
data_chunks: R script put csv files chunked for future use.
R: A script is located here.
results: R script outputs a result of URL check as one file here.
results_chunks: R script outputs a result of each chunked file here. Check here to know how many files have been through.

Run the code in `R/check_url_in_chunks.R`, after adjusting name of the input data file and number of chunks as needed. Values needed to be adjusted are:
Line 138 and 139: Enter a column name of where URL data is in. Add/delete a line accordingly (Default values are 'dc.publisher.uri' in line 138 and 'dc.relation.uri' in line 139)
Line 160: Enter a csv file name
Line 171: Specify 'n_chunks' value (default is 100)
Line 187: Change a value in 'data_files' accordingly; Default [1:100] means to load a file from 1 to 100.

Please note that at the beginning of the run, it shows eta, but it is not so accurate.
If R script stopped running without output under results folder, check results_chunks folder and adjust line 187 so it can resume from where it stopped.
