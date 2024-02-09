# csv2nwb: An initiative for converting Lab's data to NWB standards through simple CSV tables
This repository contains the codes to convert acquired and processed data into NWB standard format, through a bridge of prestructured csv tables.

## Description
From the beginning, the idea was to simplify the process of converting the lab's data to NWB standards while the experimenter has nothing to do with the coding. The approach was to fill the gap between non-expert-in-coding experimenters and the PyNWB API, through a specific while flexible set of structured CSV Files -accessible and easily usable by everyone. By using this base pipeline of conversion, the experimenter would have nothing to do with the coding whatsoever, ergo making it user-friendly, ergo more people in the community can use it to participate in NWB standardization.

Meta-data for each data-set serves as a keyed dictionary to feed PyNWB classes in an optimized way; Also allowed to be extended based on the experimenter’s opinion with extra keys. (Just add column to .CSV!)
Although, as a showcase, this base pipeline is initially set to serve the specific data types at DCL -mainly concerned with behavioral analysis, one would find it easily extendable to the most general purpose. After all, the data produced by a single lab would only require a few number of functions/modules from the API, so arguably easily adjustable to any lab's needs only by adjusting the pre-defined csv templates and the `base-func-sheet.py` module.
 
The most important advantage of this initiative is to interactively communicate with the experimenter through a few pre-structured tables (.csv) without the need to get into coding, whatsoever. 

## Usage
To start using the package:
1.  I recommend to set up a new [conda environment](https://docs.conda.io/en/latest/miniconda.html) with the following dependencies:

* pynwb

2. install the csv2nwb package from this repository by simply cloning and installing it locally,
```
git clone https://github.com/Hamidreza-Alimohammadi/csv2nwb.git

pip install .
```
while in the cloned directory.

3. now, the package should be installed in your environment. initiate python and simply start with:
```
from csv2nwb import main

main.generate_templates()
```
this would generate the templates folder in `./data` containing the pre-structured tables and for all sessions these files should be updated separately. I would recommend to keep up with the naming conventions and saving the sessions in a tree like directory and only copy the new session's data onto tables. Note that one needs to simultaneously sync main-data and their associated meta-data. No `nan`s should 
be given values.

4. get started with the conversion:
```
main.start_conversion()
```
an interactive dialog-box would appear to choose the root directory of the experiment containing all the sessions, choose it and all is done! an exact replica of the directory tree would be created
on the same directory level of the selected root marked with the time of conversion, including separate nwb files. For a test run, you could navigate to the `./data/test-example/test-root` (hypothetical experimental sessions) and just hit select, from thereon it will automatically convert all the sessions and save it to the folder on the same directory level of the `test-root`.

## Use cases
A functional project-oriented use case of this initiavtive is `dcl2nwb` [find it here](https://github.com/Defense-Circuits-Lab/dcl2nwb).

## Author
* Hamidreza Alimohammadi (alimohammadi.hamidreza@gmail.com)

## Version History

* 0.1.0


