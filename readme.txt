NWEN304 PROJECT 2 APPLICAITON
STATUS O'BRIEN
300350413

The application that you are using is very simple. It has been uploaded heroku
located at the folowing url:.
https://limitless-brushlands-90934.herokuapp.com/

The database used for the website is located on the heroku servers. Our server
connects to this database and begins storing or transferring data depending on
the users interaction.

The website(index.html) and all its relevant files, are located where the server is located,
(which is currently the heroku servers). When you launch the website using the link above, you are
connecting directly with the server, which then fetches the website you are seeking, and returns it
to the user, who is then able to browse the site.

The REST API functions are located in the same file as the server (index.js). They contain, GET,
POST, PUT, DELETE commands. They are accessed by the client via AJAX calls. It then retrieves or places
the relevant information you are asking for in the database.

An ajax call to GET, retrieves all the tasks stored in the database.
An ajax call POST/, inserts entries into the databse.
An ajax call DELETE/, removes entries from the database.
An ajax call PUT/update_task, updates an entry in the database,
An ajax call PUT/place_task, updates an entries categroy.

Test cases were created to test the implementation of this application. I have taken the time to create
a runnable bash script to execute the curl commands automatically. This is located in the working directory
and can be run using:
./test_cases.sh

The test cases interact with the heroku db on their servers. They are ready to be used at your will.

I have also added the test commands below:

# Place task in db
curl -H "Content-Type: application/json" -X POST -d '{"cat":"1","item":"task placed"}' https://limitless-brushlands-90934.herokuapp.com/tasks

#Get tasks from db
curl -H "Content-Type: application/json" -X GET https://limitless-brushlands-90934.herokuapp.com/all_tasks

#Update task in db
curl -H "Content-Type: application/json" -X PUT -d '{"previous":"task placed","current":"updated task"}' https://limitless-brushlands-90934.herokuapp.com/update_tasks

#Change task categroy in db
curl -H "Content-Type: application/json" -X PUT -d '{"item":"updated task","cat":"1"}' https://limitless-brushlands-90934.herokuapp.com/place_tasks

#Remove a task from the db
curl -H "Content-Type: application/json" -X DELETE -d '{"item":"updated task"}' https://limitless-brushlands-90934.herokuapp.com/delete_taskst
