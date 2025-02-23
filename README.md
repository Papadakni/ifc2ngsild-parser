# Iotspaces-IFC2NGSI-LD_parser

parcer.py is a program that generates NGSI-LD instances of buildings (floors, rooms, windows, doors) from an .ifc file using the IfcOpenShell and Shapely libraries.

(NOTE: It could be that the .ifc file provided doesn't contain the appropriate relationships in order to find corellations between rooms with windows, doors etc.. In that case you should enable the experimental geometrical comparison function be running the parser with the -t flag)

## Docker image

There is a provided docker image template, you can generate it for usage with the following command

```
docker build -t ifc2ngsildparser .
```

## Installation

To install the dependencies required to run this program, use the following command:

```
pip install -r requirements.txt
```


## Usage

To run the program, use the following command:

```
python parcer.py -f <filename> [-t] [-d]
```
### Arguments

* `-f` or `--file`: Specifies the name of the input .ifc file to use/convert.
* `-t` or `--test`: Enables internal experimental functions.
* `-h` or `--help`: Displays the usage message.
* `-d` or `--2D`: Changes the result from 3D to 2D. Note that this option has some issues, so the default 3D is preferred.

### Example Usage

To generate NGSI-LD instances from an .ifc file named "building.ifc" with the default 3D output, use the following command:

```
python3 parcer.py -f building.ifc
```

To generate NGSI-LD instances from an .ifc file named "building.ifc" with 2D output, use the following command:

```
python parcer.py -f building.ifc -d
```
