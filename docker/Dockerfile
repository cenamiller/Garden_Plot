# Use an official lightweight MPI image
FROM ubuntu:22.04

# Install MPI
RUN apt-get update && apt-get install -y mpich && rm -rf /var/lib/apt/lists/*

# Set the working directory
WORKDIR /app

# Copy the application code from the src folder
COPY src/ .

# Compile the MPI program
RUN mpicc -o hello_mpi hello_mpi.c

# Define the default command
CMD ["mpirun", "-np", "4", "./hello_mpi"]
