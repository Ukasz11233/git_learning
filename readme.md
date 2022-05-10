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
###
- __git commit -m "tresc_komentarza"__ ---> dodaje pliki z przechowalni do repozytorium
wraz z treścią komentarza

### Przywracanie zmian:  
- __git checkout:  
-- file_name__ == __git restore__ --> przywraca plik z katalogu roboczego do stanu aktualnego w  
__commit hash__  --> przestawia wskaźnik katalogu roboczego HEAD na _commit hash_, czyli w katalogu roboczym wyświetlane 
  są pliki które były podczas danego commitu.  
__commit hash__ __file_name__ --> przywraca dany plik _file_name_ do aktualnego katalogu roboczego.
repozytorium  
- __git revert__:
__commit has__ --> odwraca zmiany w wybranym commicie i zapisuje je jako nowy commit.
  Za jego pomocą można odwracać zmiany w repo publicznym, ponieważ nie modyfikuje historii commitów.
- __git reset__:  
== __git restore --staged__  ---> usuwa pliki z przechowalni (odwrotność __git add__) 
__--mixded hash_commit__ --> wszystkie nowsze commity zostaną usunięte, a zmiany wprowadzone podczas
  tych commitów zostaną odzwierciedlone w naszym katalogu roboczym
__--soft hash_commit__ --> tak jak wyżej, tylkko, że zmiany zostaną dodane do poczekalni.
__--hard hash_commit__ --> wszystkie commity i zmiany zostaną bezpowrotnie usunięte.  
    

- __git rm\mv file_name__ ---> usuwa\przenosi z repozytorium plik file_name. Następnie informacja o tym 
zostaje dodane do przechowalni

###
- __git clean__ ---> usuwa nieśledzone pliki i katalogi @__!!! nie moze sotac odwrocone!!!__@:  
-n --> wyświetla pliki które będą nieśledzone (tryb testowy polecenia git clean)  
-d --> wyświetla katalogi  
-i --> tryb interaktywny

##Pliki:
.gitignore ---> zapisane w nim pliki sa ignorowane przez system kontroli wersji