


Runing logstash with docker build:

    $ docker build -t logstash:csv .
    $ docker run --entrypoint "/bin/sh" -it logstash:csv
    $ bin/logstash -f load-csv.conf --verbose
	
Copy logstash config from host to logstash server:

    docker cp <file> <container id>:<container path>
    
	$ docker cp C:/dev/wks/wks-b3/b3-stocks/load-csv-logstash.conf 066:/usr/share/logstash/pipeline/stocks.conf
	$ docker cp C:/dev/wks/wks-b3/b3-stocks/data/BBAS3M.SA.csv 066:/usr/share/logstash/data/BBAS3.SA.csv
	$ docker exec -it 066 logstash -f /usr/share/logstash/pipeline/stocks.conf
	
	
	
	
	
