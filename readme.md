GIT-TUTORIAL
https://www.youtube.com/watch?v=Uszj_k0DGsg
https://www.udemy.com/course/versionsverwaltung-mit-git-und-github-fur-anfanger/learn/lecture/19451080#overview

clients von Anbieter  http://git-tower.com
http://github.com
gitlab.com
bitbucket.com

//ACHTUNG MIT PASSWÖRTERN + URLS 
etc. dürfen nach Möglichkeit gar nicht erst im Code auftauchen
es hilft dann auch nicht wenn sie nur in der aktuellen Version
einer Datei nicht mehr verfügbar sind.
 
//Dinge an die man sich gewöhnen muss
1. sobald man den Branch der Entwicklung ändert wird auch diese version in bei der Benutzung der Software aktiv.  Das mach manches einfacher, kann aber auch Verwirrung stiften, wenn man nicht darauf geachtet hat, dass in welchem branch man ist. Zusätzliche Aufmerksamkeit  - wie bei Cachefehlern.
2. Nach Änderungen immer ein git status  und anschließend die Änderungen an den verschiedenen Dateien einzeln oder gesamt commiten
3. Immer (!) ein Pull von der im Github liegenden Variante holen. Hierbei Achtung mit den verschiedenen Branches
//Wenn man im Team arbeitet
  1) immer ein fetch - um zu checken, was haben die anderen getan
  2) pull - um aktuelle Ressource herunterzuladen   3) push um Ende eines Arbeitstages…

	

//config eigene Angaben
git config --global user.name „<name>„
git config --global user.email „<email>„

// .gitignore

*.a // ignore all .a files
!lib.a // but do track lib.a, even though you're ignoring .a files above
/TODO // only ignore the TODO file in the current directory, not subdir/TODO
build/ // ignore all files in any directory named build
doc/*.txt // ignore doc/notes.txt, but not doc/server/arch.txt
 doc/**/*.pdf // ignore all .pdf files in the doc/ directory and any of its subdirectories

//init
git init
legt eine Versionsverwaltung für das aktuelle Projekt an

//commit
git commit <file>
Achtung beim commit öffnet sich der VI-Editor (esc-taste drücke und dann :wq eingeben dann enter)
wenn man nicht speichern will esc-taste :q! enter
besser:
git commit  -m „das habe ich getan“ <file>

//LOG 
Änderungen anzeigen
git show 
mit der option s 
bzw. 
git log —online (bessere verkürzte Darstellung) 
einzeilige Darstellung der Änderungen
git log --graph --online (mit grafischem Baum)

//DIFF
Was geht ab …oder…kommt hinzu 
git diff <code des commits/reverts aus dem Log>

//REBASE
eher nicht verwenden - sorgt für 

//RESTORE
Stellt gelöschte Dateien wieder her
git restore <dateiname>

//REVERT
Alten Zustand einer Datei wiederherstellen 
git revert <code des commits/reverts aus dem Log>

//BRANCH
Anlegen von branches bzw. forks
git branch  <name>
In einen branch wechseln
git checkout <name>
Löschen eines Branches
git branch -D <name> 
//STASH
um Zwischenstände zu speichern bzw. Alternativen auszuprobieren
Wichtig! Dem stash muss ein commit der Datei(en) vorangegangen sein.
git stash save <name> 

Vorzugsvariante reaktivieren
a) git stash list
stash@{1} ….
stash@{2} ….
b) git stash apply stash@{2}
c) git stash clear (löschen des Stashs)

//MERGE
man bereinigt die Datei… und macht ein commit …
Danach läßt man sich mit git status den aktuellen Status ausgeben.
Wenn alles 0kay ist kann es weiter gehen.

vereinbaren von regeln/Konv. für die Arbeit mit Repos.

GITHUB FLOW
Normalerweise lassen sich alle Entwicklungsumgebungen
man holt sich bevor man zu arbeiten anfängt erst mal die neuesten
Änderungen von Server ab

 //clone
Arbeitskopie  eines Projektes von anderem Entwicklers herunterladen
Achtung!! -  die Kopie wir in das Verzeichnis gepackt, das gerade aktiv ist 
git clone <https://>

//fetch (immer vor pull)
überprüfen des Status zwischen lokaler und GitHub-„Instance“
am besten vor jedem „pull“ ausführen - vor allem wenn man in Teams arbeitet..
git fetch origin  <name des branch>
git status //danach wird es eventuell Informationen über Änderungen geben

//pull
damit holt man sich die aktuelle Ressource merged eventuelle Änderungen
git pull origin <name des branch>


//push
damit legt man die Änderungen im Online-Repository ab…

//wenn der lokale code hochgeladen werden soll in ein frisches  repository
git remote -v git remote set-url origin <url des angelegten repos *>
git remote remove origin //Löschen der online history und der Dateien
git remote add origin <url des angelegten repos *>
git branch -M main //festlegen des Master-Branches
git push -u origin main //main synchronisieren bzw. lokalen branch main hochladen

//wenn der branch online noch nicht existiert…
git push -u origin <name>

// Releases on GITHUB
//local steps
git tag -a v1.0 -m "Release version 1.0"
git push origin v1.0
//GITHUB unter Code -> Releases
wichtig latest version…stable version..etc.

CODE ISSUES PULLREQUEST



*zum Beispiel:  https://github.com/clanghof/git-kurs.git



