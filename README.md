# IntelLiGent-Data-Standard

This repository introduces a standard for contextual data-sharing between IntelLiGent project partners.

The repository contains:
- an overview of a conventional data pipeline for sharing experimental battery test data,
- a template for the creation of human- and machine-readable metadata in the JSON-LD file format, and
- details on the directory naming conventions.

# Overview

A conventional data pipeline for experimental electrochemical battery testing is presented below. The top row of containers represents the standard data structures that are generated and stored during the process. This is one potential representation; however, the divisions between these discrete containers aren't fixed. For example, the electrochemical data container and cell properties container could be stored as one in certain workflows. 

![Alt text](./assets/Data_Structure.svg)

In the above figure, the blue containers denote the finalised structure for sharing data between partners. The hatched "Parquet" container offers a potential improvement over the "CSV" container in regards to storage size and access speed; however, reduced human readability. Conversion from CSV to the Parquet file format can be achieved using the conversion scripts available in our [file-format-conversion](https://github.com/Battery-Intelligence-Lab/file-format-conversion) repository.

# Metadata File

Alongside the battery test data, a metadata file is required to store information such as the cell properties and details of the experimental protocol used to obtain the data. Metadata can be organised and therefore easily accessed when it is entered into a standard JSON file. An example [minimal JSON file](https://github.com/Battery-Intelligence-Lab/IntelLiGent-Data-Standard/blob/main/example/2023-04-10_Oxford_drF73t.json) is included in this repository to show how the structured format makes it easy to find and retrieve information. JSON files can be opened and edited in any text editor or an integrated development environment (IDE) such as Visual Studio Code.

# Naming Conventions

The directory structure for storing the metadata (JSON) and data (CSV) defined in the above figure is presented in the figure below. 

![Alt text](./assets/Directory.svg)

This structure utilises universally unique identifiers (UUIDs) to differentiate items while enabling future knowledge tree integration. By incorporating a UUID into the individual test directory, the encompassing data files don't need to have unique identifiers; however, we recommend these are labeled for human understanding.

Tools to generate the unique identifier include,
- [Short Unique](https://shortunique.id/)
- [Short-UUID](https://www.npmjs.com/package/short-uuid) (Javascript)
- [ShortUUID](https://pypi.org/project/shortuuid/) (Python)

# Acknowledgements

This repository was first created at the University of Oxford in 2023 with funding support from the Faraday Institution Multi-Scale Modelling Project (grant number FIRG059) and the EU IntelLiGent Project.

