# Dataset Summary

Name: Butterfly-Sample
Description: 
The `Butterfly-Sample` dataset contains images of butterfly specimens along with metadata including species, subspecies, sex, and type status. 
Modalities: Image; Text
Formats: `imagefolder`
Size: <1K
Libraries: `Datasets`; `Croissant`
License: `MIT`
Repository: https://huggingface.co/datasets/egrace479/Butterfly-Sample
# Dataset Structure

```
Butterfly-Sample/
├── images/
│   ├── KDS000000.tif
│   ├── KDS000001.tif
│   ├── KDS000008.tif
│   ├── KDS000009.tif
│   ├── ...
│   └── [more image files]
├── .gitattributes
├── README.md
└── metadata.csv
```
# Dataset Instances

Filename Pattern: KDS{######}
Data Format: .tif
Size: ~20 kB
Metadata: `/metadata.csv` provide the associated metadata, containing fields: `id`,  `NHM specimen number`, `view`, `species`, `subspecies`, `sex`, `type status`, `md5`.
# Data Fields

| Field Name          | Description                                                                 | Data Type | Example Values                     |
| ------------------- | --------------------------------------------------------------------------- | --------- | ---------------------------------- |
| image               | butterfly specimensm image                                                  | tif       | Not Applicable                     |
| id                  | Unique identifier for the image                                             | String    | "KDS000000"                        |
| NHM specimen number | Specimen number from Natural History Museum                                 | Int64     | 10428329                           |
| view                | Image view type (e.g., "dorsal", "ventral")                                 | String    | "dorsal"                           |
| species             | Butterfly species (e.g., "melpomene", "erato")                              | String    | "melpomene"                        |
| subspecies          | Butterfly subspecies(e.g., "etylus", "guarica", "melpomene", "thelxiopeia") | String    | "thelxiopeia"                      |
| sex                 | Sex of the specimen (e.g., "male", "Female", "female)                       | String    | "male"                             |
| type status         | Type status of the specimen                                                 | String    | null                               |
| md5                 | MD5 hash of the image file                                                  | String    | "bfe69135302b78cef66df623ddb5befd" |

# Dataset Creation

The images and accompanying metadata are originally sourced from
* Hoyal Cuthill, Jennifer F. et al. (2019), Data from: Deep learning on butterfly phenotypes tests evolution’s oldest mathematical model [Dataset]. Dryad. https://doi.org/10.5061/dryad.2hp1978.
* Hoyal Cuthill, J.F., Guttenberg, N., Ledger, S., Crowther, R. & Huertas, B. (2019), Deep learning on butterfly phenotypes tests evolution’s oldest mathematical model, Science Advances, 5(8),eaaw4967. DOI:10.1126/sciadv.aaw4967.
This dataset is a subset of images used for the Imageomics Data Training Workshop with some modifications to the metadata; it is not intended for use as more than a toy instructional dataset. The metadata provided here has been modified from the original source and image filenames have been changed.
# Data Splits
This dataset contains a single training split for instructional use. The training set contains 52 instances. 