git submodule add https://github.com/DucMinhNgo/audio-generation audio-generation
git submodule add https://github.com/DucMinhNgo/voice-generation voice-generation
git submodule add https://github.com/DucMinhNgo/frontend-music-generation frontend-music-generation

git submodule update --init --recursive git submodule update --recursive --remote 
git submodule update --init --recursive --remote

# Start Project
cd voice-generation
# Create Redis
docker-compose up -d
cd notebooks

# Run AI funtion
python queue_service.py

# Run Backend Flask (run on port: 5000)
python server.py

# Run Frontend (run on port: 3000)
cd frontend-music-generation
yarn
yarn dev
