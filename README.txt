INTRODUCTION
============
System for SenticNet Semantic analysis Challenge Task#2. It is supposed to take input in the form of a text
file and output concepts extracted from the each of the sentence in the required format mentioned at the challenge website (http://sentic.net/challenge/).

REQUIRMENTS
===========
The system requires at least Java and Python, and has been tested with the following configurations:

1. Windows 7
	- Java  version 7 update 45
	- Python 2.7.5
2. Windows 8
	- Java version 7 update ...
	- Python ....
	
3. Mac
	- Java version 7 update
	- Python

4. Linux Server
	-
	-
	
FOLDER CONTENTS
===============
This folder 'SinicaSemanticParser' contains the following folders:

	1. classifier
	2. data
	3. headFinder
	4. input
	5. models
	6. output
	7. system
	8. temp
	9. tools
	
INSTRUCTIONS TO RUN THE SYSTEM
==============================
1. Please download Stanford Parser version 3.3.1 from this link (http://nlp.stanford.edu/software/lex-parser.shtml#Download), 
extract it and put the resulting 'stanford-parser-full-2014-01-04' folder in the 'SinicaSemanticParser' folder.

2. Please download 'apache-opennlp-1.5.3-bin.zip' from here (https://opennlp.apache.org/cgi-bin/download.cgi)
extract it and put the resulting 'apache-opennlp-1.5.3' folder in the 'SinicaSemanticParser' folder.

3. From the command prompt go into the 'SinicaSemanticParser/system' folder and compile java programs with the following command

>javac -cp .;..\stanford-parser-full-2014-01-04\stanford-parser.jar;..\stanford-parser-full-2014-01-04\stanford-parser-3.3.1-models.jar;..\classifier\maxent\lib\trove-3.0.3.jar;..\apache-opennlp-1.5.3\lib\opennlp-maxent-3.0.3.jar *.java

4. Now run the 'ConceptExtractorServer' with the following command

>java -cp .;..\stanford-parser-full-2014-01-04\stanford-parser.jar;..\stanford-parser-full-2014-01-04\stanford-parser-3.3.1-models.jar;..\classifier\maxent\lib\trove-3.0.3.jar;..\apache-opennlp-1.5.3\lib\opennlp-maxent-3.0.3.jar ConceptExtractorServer

You should see the following message:

"Loading parser from serialized file edu/stanford/nlp/models/lexparser/englishPCF
G.ser.gz ... done [2.4 sec].
Server Initialized, Waiting for input..."

Leave this server running.

5. Open another command line terminal, go into the 'SinicaSemanticParser/system' folder and start 'featureExtractorServer' by using the following command:

>python featureExtractorServer.py

You should see the following message:

"Loading...
Ready!"

Leave this server running

6. Now place your input file in the  'SinicaSemanticParser\input' folder and name it input.txt

7. Open another command line terminal, go into the 'SinicaSemanticParser/system' folder and run the 'ConceptExtractorBatchClient' by issuing the following command:

>java -cp .;..\stanford-parser-full-2014-01-04\stanford-parser.jar;..\stanford-parser-full-2014-01-04\stanford-parser-3.3.1-models.jar;..\classifier\maxent\lib\trove-3.0.3.jar;..\apache-opennlp-1.5.3\lib\opennlp-maxent-3.0.3.jar ConceptExtractorBatchClient

If everything goes well, you should see the following message:

SocketClient initialized
Processing......
Done!

8. The output has been stored in the 'SinicaSemanticParser\output\output.txt'.





