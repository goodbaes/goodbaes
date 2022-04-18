version: "2.1"
services: 
  webtop:
    image: ghcr.io/linuxserver/webtop:ubuntu-mate 
    container_name: webtop
    environment:
      - PUID=0
      - PGID=0
      - TZ=America/Chicago # your timezone volumes:
    volumes:
      - /home/ruslan/webtop:/config
    ports:
      - 3000:3000
    shm_size: "2gb"
    restart: unless-stopped 
    env_file:
      .env
