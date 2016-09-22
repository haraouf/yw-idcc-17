# dataone-ahm-2016-poster
Runnable examples of YW provenance queries highlighted in poster for DataONE AHM 2016.

# Introduction

The purpose of this demo is to demonstrate the `Yesworkflow` (YW) query ability to use the `prospective provenance` created by YW and the `retrospective provenance` together to answer queries that can not be answered solely by prospective provenance or retrospective provenance.

The prospective provenance in this demo is created by YW which models conventional scripts and programs as scientific workflows. YW can provide a number of the benefits of using a scientific workflow management system without having to rewrite scripts and other scientific software. A YW user simply adds special YW comments to existing scripts. These comments declare how data is used and results produced, step by step, by the script. Then, YW interprets these comments and produces graphical output that reveals the stages of computation and the flow of data in the script.

There are various approaches to capture the retrospective provenance. Retrospective Provenance Observables, e.g., from `DataONE RunManagers` (file-level), `ReproZip` (OS-level), or `noWorkflow` (Python code-level) only yield isolated fragments of the overall data lineage and processing history. In this demo, two types of retrospective provenance observables are used: `yw-reon` and `DataONE RunManager`. The `yw-recon` can search the file system for files that match the URI templates declared for @IN and @OUT ports in the script. On the other hand, `DataONE RunManager` can authorize a list of input and output files for a script run. 

# Layouts of Repository

| Directory | Description                                                          |
|-----------| :--------------------------------------------------------------------|
|examples/ |   Contains examples demonstrating the queries in the queries folder |
|queries/ | it stores the scripts to the five demo queries we asked.|
|rules/| it contains a set of Prolog rules for generating prospective yesworkflow views rules (`yw_rules.P` and `yw_views.P`), retrospective reconstructed rules (`recon_rules.P`), graph rendering rules (`gv_rules.P`), and populating graph rules (`yw_graph_rules.P`).|

The example subfolders also have a typical folder structure:

`dataone-ahm-2016-poster/examples/<my_example>/` 

Subfolders that all `<my_example>` folders have:

| Directory | Description                                                          |
|-----------| :--------------------------------------------------------------------|
| script/ | the example script or scripts that make up  <my_example> |
| facts/ | the YW facts for <my_example>, generated by running YW on the example script(s)|
| views/ | materialized views for <my_example>|
| recon/ | reconstructed provenance used for <my_example>|
| results/ | all artifacts generated by make.sh|
|supplementary/ | a folder with supplementary files and information about the example|
| clean.sh | removes generated demo artifacts for <my_example> |
| make.sh | creates demo artifacts for <my_example> |

Note: after running `clean.sh` and `make.sh`, you can use git status to see what demo artifacts have just been created.

# Installing, Browsing, and Running the Demo

1. Clone the `dataone-ahm-2016` git repo to your local machine using the command:`git clone https://github.com/idaks/dataone-ahm-2016-poster.git`

2. Copy your example folder under examples/ folder. There are already three examples there:  `C3C4`, `LIGO`, and `simulate_data_collection`.

3. Reorganize your directory layout for your twitter use case to be the same as `C3C4`, `LIGO`, and `simulate_data_collection`. Create a `recon/` folder which contains your `reconfacts.P`.

```
simulate_data_collection/
├── clean.sh
├── facts
│   ├── yw_extract_facts.P
│   └── yw_model_facts.P
├── make.sh
├── results
├── script
│   ├── calibration.img
│   ├── cassette_q55_spreadsheet.csv
│   └── simulate_data_collection.py
└── views
    └── yw_views.P
 ```
 
4. Copy two script files `clean.sh` and `make.sh` from the `simulate_data_collection` of the existing three examples to your own example folder. 

5. Open `make.sh` and customize the scripting name, outputfile name, parameter data object name to your example.

6. Run `bash make.sh`.
    

# Demo Queries

Please read [Query README](https://github.com/idaks/dataone-ahm-2016-poster/blob/master/queries/README.md) in the demo repo.
