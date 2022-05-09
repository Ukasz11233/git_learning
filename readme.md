### Lokalne repozytorium:

- katalog roboczy (working directory)  
  |  git add .  
  V  
- przechowalnia (staging area)  
  |  git commit  
  V
- repozytorium (.git folder)   

### Trzy stany plików:  
- zmodyfikowane (modified)  
  |  git add  
  V         
- śledzone (tracked)
  |  git commit
  V 
- zatwierdzone (commited)


#### *Bilokacja pliku:

Jest to sytacja w której dany plik jest zmodyfikowany oraz śledzony
(czyli znajduje się w katalogu roboczym oraz w przechowalni jednocześcnie, pod dwoma różnymi formami)  
Do sytacji dochodzi gdy zrobimy:  
- git add file
- _modyfikujemy plik: file_
- git status pokazuje nam, że plik znajduje się w dwóch miejscach

Aby rozwiązać ten problem wystarczy zrobić __git add file__ lub __git commit__,


##Commands:
- git init ---> inicjalizuje puste repozytorium lokalne
- git status ---> sprawdza status plikow w repozytorium lokalnym
- git add .  ---> dodaje wybrane pliki do przechowalni 
- git commit -m "tresc_komentarza" ---> dodaje pliki z przechowalni do repozytorium
wraz z treścią komentarza
- git clean ---> usuwa nieśledzone pliki i katalogi:  
-n --> wyświetla pliki które będą nieśledzone (tryb testowy polecenia git clean)
-d --> wyświetla katalogi
-i --> tryb interaktywny
- git reset ---> usuwa pliki z przechowalni (odwrotność __git add__)   
##Pliki:
.gitignore ---> zapisane w nim pliki sa ignorowane przez system kontroli wersji