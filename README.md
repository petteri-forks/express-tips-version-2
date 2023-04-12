# Introduction

This project contains some sample GitLab CI/CD pipelines that demonstrate different CI/CD features.

# Samples

## TotD

Tip of the Day service contains a script to be run with every login to a bash environment - linux server, WSL, etc.
It contains the actual tips files and the script. Both are deployed to remote hosts, either for user specific or host wide use. The pipeline build the service by "compiling" the tips files to simple enumerated versions, tests the script and deploys it to remote server.

## TotD version 2 instructions

create .env file in the nodeapp folder with values:
DB_PORT=5432
DB_HOST=localhost
POSTGRES_USER=user
POSTGRES_PASSWORD=password
POSTGRES_DB=tips

run "docker compose up" in the root directory of project
navigate to nodeapp/scrips
run "node add_data_to_db.js"

in the nodeapp folder run "node app.js" to start webserver

endpoints

Get all tips (GET)
http://localhost:3000/getall

Delete tip by Id (DELETE)
http://localhost:3000/:tid/delete

Update tip by Id (PATCH)
http://localhost:3000/:tid/update

Get tip by Id (GET)
http://localhost:3000/:tid

Get tip by Id as plain text (GET)
http://localhost:3000/:tid/plain

Add new tip (POST)
http://localhost:3000/addtip


# Links and References

* https://docs.gitlab.com/ee/ci/pipelines/
* https://docs.gitlab.com/ee/ci/ssh_keys/
* https://www.udemy.com/course/gitlab-ci-pipelines-ci-cd-and-devops-for-beginners/



