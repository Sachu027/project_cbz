version: '3.8'

services:
  # Backend Service
  backend:
    build: ./backend
    ports:
      - "8080:5000"   # EC2:8080 -> Backend:5000
    environment:
      - MONGO_URI=mongodb://db:27017/todo
    depends_on:
      - db

  # Frontend Service
  frontend:
    build: ./frontend
    ports:
      - "80:3000"     # EC2:80 -> React:3000
    environment:
      - REACT_APP_BACKEND_URL=http://your-ec2-ip:8080
    depends_on:
      - backend

  # Database Service
  db:
    image: mongo:latest
    # No ports exposed (internal only)
