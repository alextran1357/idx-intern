# List of transformations
## market_analysis_fields column filter
I looked ahead at what we are trying to do to determine what to keep. Other than that, the rest of the columns aren't chosen under any strict rules, just on how I feel.
* Listing: **(540831, 86) -> (540831,43)**
* Sold: **(397540, 86) -> (397540, 47)**
  
## null_90_columns column filter
Any column over 90% null rate were removed
* Listing: **(540831, 43) -> (540831,33)**
* Sold: **(397540, 47) -> (397540, 35)**

## dup_columns column filter
Any columns that were duplicates of another column or is no long needed were removed
* Listing: **(540831, 33) -> (540831, 29)**
* Sold: **(397540, 35) -> (397540, 31)**

## date and geographic consistency
Create flags to mark those with inconsistent dates progression and incorrect geographic locations
* Listing: **(540831, 29) -> (540831, 32)**
* Sold: **(397540, 31) -> (397540, 34)**

## negative_filter
any important numeric columns were checked for negatives and removed
* Listing: **(540831, 32) -> (538280, 32)**
* Sold: **(397540, 34) -> (396216, 34)**

## inconsistent_filter
checked that the postal code was not 0 and that all states were within California
* Listing: **(538280, 32) -> (538075, 32)**
* Sold: **(396216, 34) -> (396188, 34)**

## Dtypes
dtypes were compared against the meta data pdf and converted to the correct dtype
