API GMAIL (r�solution des probl�mes d'installation)

- liste des erreurs lors du git clone :


A> ERREURS D'INSTALLATION:

1/

internal/modules/cjs/loader.js:573
    throw err;     ^
Error: Cannot find module 'googleapis'

>>>installer les modules compl�mentaires ('node modules'):
npm install


2/

found 25 vulnerabilities (2 low, 21 moderate, 2 high)

>> R�paration des Vuln�rabilit�s :
npm audit
npm audit fix
npm audit fix --force (au besoin ??)

>>puis r�parations manuelles si possible :
npm update
modifier le num�ro de version dans 'package-lock.json' (attention si on refait un 'npm audit fix', il peut remettre l'ancienne version avec vuln�rabilit�)
npm update --save hoek (exemple d'update individuel)
npm outdated
npm install npm@6.2.0


3/

-"TypeError: googleAuth is not a constructor"
 at authorize (/home/yanniscode_bzh/Documents/code.bzh/projets/sakana/Node-Extract_SQL_Insert-b/quickstart-2.1.js:135:16)

>>> mise � jour de Node.js (npm i npm) et de certains modules :

npm install googleapis --save
npm install google-auth-library@0.* --save


B> ERREURS DE CONFIGURATION :


1/

59 - Erreur du chargement du fichier "client secret": Error: ENOENT: no such file or directory, open 'client_secret.json'

>>> r�cup�rer le fichier 'client-secret' sur gmail et le placer � la racine du projet


2/

events.js:167
      throw er; // Unhandled 'error' event
      ^
Error: Unknown database 'test_sakana'
    at Packet.asError (/home/yanniscode_bzh/Documents/code.bzh/projets/sakana/Node-Extract_SQL_Insert-b/node_modules/mysql2/lib/packets/packet.js:716:13)

>>> cr�er la base de donn�e MySQL en copiant/collant le fichier 'datafishuk.sql' dans la console ou Phpmyadmin


3/

fs.js:110
    throw err;
    ^
Error: ENOENT: no such file or directory, open '/home/yanniscode_bzh/Documents/code.bzh/projets/sakana/Node-Extract_SQL_Insert-b/Tableaux/xlsx/fichier-sakana-whitform-22_7_2018-20__1.xlsx'
    at Object.fs.openSync (fs.js:545:3)
    at Object.fs.readFileSync (fs.js:451:33)
    at read_binary (/home/yanniscode_bzh/Documents/code.bzh/projets/sakana/Node-Extract_SQL_Insert-b/node_modules/xlsx/xlsx.js:1891:44)

>>> cr�ation des r�pertoires 'csv' et 'xlsx' dans le dossier 'Tableaux'



*****************

NOUVELLE ERREUR dans le module 'quickstart-2.1.js' de 'ukquota.dataviz.fish' - status = irr�solu 

-TypeError: Cannot read property 'length' of undefined at /home/yanniscode_bzh/Documents/code.bzh/projets/sakana/ukquota.dataviz.fish/quickstart-2.1.js:261:61

> pas d'enregistrement des fichiers dans les r�pertoires > question de droits ?? - 21/07/2018


