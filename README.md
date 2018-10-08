# Early Modern Letters Online (EMLO)

Docker containers for converting EMLO CSV files into RDF format and publishing it in Fuseki.

The EMLO CSV data files have to be in the `data` directory.

## Convert

`docker-compose up emlo-converter`

## Load data into Fuseki

`docker-compose run --rm emlo-fuseki ./load_data.sh`

## Run Fuseki

`docker-compose up emlo-fuseki`
