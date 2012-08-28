Pongo = Postfix + MongoDb
=========================

Introduction
-----------
Pongo is a tool developed at Youzee.com intented to allow Postfix's access(5) 
lookup utility read from a mongo database. For accomplishing this, it implements Postfix's 
tcp\_table(5) interface.


How it works
------------
Once run with the correct arguments, it will start a main process and a pool of workers that will each one create
its own connection to the mongo database. Then for every request in tcp\_table(5) format sent to the listening process
a worker will query the database for the provided KEY value and will return even a 200 followed by the (specified by -s)
discard string if the key was found or a 500: not found if it was not in the collection.


Installation
------------
  1. Download and uncompress pongo-VERSION.tar.gz from the dist/ directory.
  2. Run ```pip -i requirements.txt``` to install the required dependencies
  3. Run ```python setup.py install``` to install Pongo.
  4. Run ```pongoserver --help``` to see the available options. 

