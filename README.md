# StayNest ADF Assignment

In this assignment I used Azure Data Factory to copy files from the raw folder into the bronze folder of my storage container (`staynest`).

## Pipelines

**pl_copy_raw_to_bronze**
Uses a Get Metadata activity (`gm_get_raw_files`) and a Copy data activity (`copy_raw_to_bronze`) to move the files from raw to bronze.

![File move](images/file_move_png.png)

**pl_copy_all_files**
Copies all the files without making a separate copy activity for each one.

1. Get Metadata reads the list of files in the source folder
2. ForEach loops through that list
3. Copy data inside the loop copies each file to the destination

![File move with ForEach](images/file_move_foreach_png.png)

## Get Metadata output

Get Metadata returned three files: `bookings.csv`, `customers.csv` and `hotels.csv`.

![Get Metadata output](images/get_metadata_output_png.png)

## Result

I ran both pipelines with Debug and all activities succeeded. The three files are now in the bronze folder.

![Bronze folder](images/bronze_png.png)
