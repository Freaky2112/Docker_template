Please edit those lines in docker-compose.yml according to your config

## your path to where 's ocker folder

- ../Dockers:/var/lib/docker:ro

## don't forget to check is your port is available and change it only the first port 

 ports:
      - "9090:9090" \
      - "3300:3000" \
      - "9100:9100" \
      - "8080:8080" \ 
      - "3100:3100" \ 
      - "12345:12345"