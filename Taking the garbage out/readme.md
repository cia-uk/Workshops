## Resources for the BSides London 2024 Taking the garbage out! Workshop

This contains the following files:
- docker-compose file to stand up Graylog
- filebeat.yml file for filebeat to ingest sample logs
- Sample logs:
    - Cisco ASA Traffic logs
    - Fortigate Traffic Logs
    - Palo Alto Traffic Logs

## Requirements:

To complete this workshop the attendee should have the following software, note these can be used on most platforms windows/linux/mac:

- Docker Desktop or similar
- Filebeat

## Quickstart:

Download the files to your working directory.

1. Stand up the docker containers using - `docker-compose -p bsides -f bsides.yml up -d` this will start the containers in a project called bsides
2. Check you can login to the Graylog web interface at http://127.0.0.1:9000 with the user and password `admin:@Grayl0g123`
3. Go to the system>inputs menu and launch a "beats" input type on port 5044, check the tickbox at the bottom to not prefix fields with beats type.
4. Place filebeat.yml and sample log files in your filebeat directory on the same host as docker
5. Run filebeat with filebeat `filebeat -e`
6. Validate logs arrive in your Graylog instance by using the search page and searching all logs.

## Re-ingest logs

To re-ingest the logs as you may wish to do multiple times for testing.

1. Delete the `data` directory within the filebeat folder.
2. Re-run filebeat
