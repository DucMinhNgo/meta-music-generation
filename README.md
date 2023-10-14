# Clone and Install Code
git clone https://github.com/DucMinhNgo/meta-music-generation

- Meta repo is module contain three submodules
    + https://github.com/DucMinhNgo/audio-generation
    + https://github.com/DucMinhNgo/voice-generation
    + https://github.com/DucMinhNgo/frontend-music-generation
# Create Redis, Server (Flask), AI (voice generation)
cd voice-generation
docker-compose up -d
cd notebooks
python server.py
python queue_service.py

# Start AI (melody generation)
cd audio-generation
python -m demos.queue_melody_service.py

# Run Frontend (run on port: 3000)
cd frontend-music-generation
yarn
yarn dev
