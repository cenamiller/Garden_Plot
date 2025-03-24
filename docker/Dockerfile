# Use an official lightweight MPI image
FROM ubuntu:22.04

# Install MPI
RUN apt-get update && apt-get install -y mpich && rm -rf /var/lib/apt/lists/*

# Set the working directory
WORKDIR /app

# Debug: List files in the build context
RUN echo "Listing files in build context:" && ls -R /app

# Copy the application code from the src folder
COPY src/ .

# Debug: Verify the copied files
RUN echo "Listing files in /app after COPY:" && ls -R /app

# Compile the MPI program
RUN mpicc -o hello_mpi hello_mpi.c

# Define the default command
CMD ["mpirun", "-np", "4", "./hello_mpi"]
