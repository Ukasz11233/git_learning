### Lokalne repozytorium:

- __katalog roboczy__ (working directory)  
  |  git add .  
  V  
- __przechowalnia \ kolejka oczekiwania__ (staging area)  
  |  git commit  
  V
- __repozytorium__ (.git folder)   

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
- __git init__ ---> inicjalizuje puste repozytorium lokalne
- __git status__ ---> sprawdza status plikow w repozytorium lokalnym

###
- __git add .__  ---> dodaje wybrane pliki do przechowalni 
- __git reset__ == __git restore --staged__  ---> usuwa pliki z przechowalni (odwrotność __git add__) 
###
- __git commit -m "tresc_komentarza"__ ---> dodaje pliki z przechowalni do repozytorium
wraz z treścią komentarza
- __git checkout -- file_name__ == __git restore__ ---> przywraca plik z katalogu roboczego do stanu aktualnego w 
repozytorium
- __git rm\mv file_name__ ---> usuwa\przenosi z repozytorium plik file_name. Następnie informacja o tym 
zostaje dodane do przechowalni

###
- __git clean__ ---> usuwa nieśledzone pliki i katalogi @__!!! nie moze sotac odwrocone!!!__@:  
-n --> wyświetla pliki które będą nieśledzone (tryb testowy polecenia git clean)  
-d --> wyświetla katalogi  
-i --> tryb interaktywny

### 
- __git log__ ---> wyświetla historię commitów:  
--oneline --> wyświetla w skondensowanej wersji
##Pliki:
.gitignore ---> zapisane w nim pliki sa ignorowane przez system kontroli wersji