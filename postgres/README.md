dockerfiles-fedora-postgres
===========================

Fedora dockerfile for PostgreSQL

1.	To build

Copy the sources down and do the build-

    # docker build --rm -t username/postgresql . |& tee postgres_build.log

2.	To run 

If port 5432 is open on your host:

    # docker run -d -p 5432:5432 username/postgresql

or to assign a random port that maps to port 5432 on the container:

    # docker run -d -p 5432 username/postgresql

To see the random port that the container is listening on:

    # docker ps

3.	To test 

To find the IP address, get the container ID:

    # docker ps

Then get the IP addr:

    # docker inspect --format '{{ .NetworkSettings.IPAddress }}' a0d14cc9830b

Now connect to the instance of PostgreSQL.  There is no default database at this time.

    # psql -h 172.17.0.x -U postgres
