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
__branch_name__ --> zmienia gałąź
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



### Przeglądanie historii:
- __git log__:  
__--oneline__ --> wyświetla historię w skondensowanej formie  
__--author="Ukasz11233"__ --> wyświetla commity danego użytkownika  
__--patch__ -- file_name__ --> wyświetla zmiany jakie zaszły w danym pliku  
__--graph --decorate --all --oneline__ --> wyświetla wszystkie commity jako graf
###
- __git clean__ ---> usuwa nieśledzone pliki i katalogi @__!!! nie moze sotac odwrocone!!!__@:  
-n --> wyświetla pliki które będą nieśledzone (tryb testowy polecenia git clean)  
-d --> wyświetla katalogi  
-i --> tryb interaktywny
  
### Stash:
- __git stash__: --> dodaje zmiany które nie zostały commitowane na stos
-d --> wyświetla katalogi  
__stash push -m "message"__  --> dodaje na stos wraz z komentarzem   
__stash list__ --> wyświetla zawartość stosu  
__stash pop__  --> zabiera pierwszy element ze stosu i dodaje do katalogu roboczego  
__stash apply stash@{1}__ --> dodaje do katalogu robczego elementy na stosie z indeksu 1
  i zostawia je na stosie.  
__stash drop stash@{2}__  --> usuwa drugi element ze stosu  
__stash clear__  --> czyści cały stos  
##Pliki:
.gitignore ---> zapisane w nim pliki sa ignorowane przez system kontroli wersji


7 zasad pisania komentarzy:  
- Podziel komentarz na tytuł oraz treść, oddzielając je pustym wierszem
- Ogranicz długość komenatrzy do 50 znaków.
- Tytuł rozpoczynaj wielką literą
- Nie dodawaj kropki na końcu tytłu
- Używanie trybu rozkazującego w treści tytułu komentarza
- Ogranicz dłguość wiersza do 72 znaków (chodzi o to, żeby edytor nie łamał wierszy)
- Pisząc treść komentarza odpowiadaj na pytania co i dlaczego 


# Branch

### Master branch:
- glowna galaz projektu wykorzystywana do publikacji najnowszej wersji projektu na serwerze produkcyjnym.
Master powinien zawsze zawierac stablina wersje produktu.
  
### Dev branch:
- galaz na ktorej znajduje sie wersja testowa projektu. Zwykle polaczona z serwerem testowym.


### Feature branch:
- galaz na ktorej prowadzone sa prace na nowymi funkcjami. Po ukonczeniu prac, trafiaja na branch dev.

### User branch:
- galezie uzytkownikow indywidualnej pracy czlonka zespolu nad zmianami. Ukonczone zmiany trafiaja na galaz feature.

### Test/Bugfix branch:
- w szczegolnych przypadkach, konieczne jest szybkie wprowadzenie zmian. W tej sytuacji wykorzystywane sa galezie
typu bugfix. Przygotowywane tutaj zmiany, najczesciej trafiaja na galaz dev.
  
## Polecenia:
- __git branch__ --> wyswietla wszystkie widoczne branch'e na lokalnym repo.  
__--delete branch_name__ -> usuwa galaz
- __git merge branch_name__ -> laczy ze soba dwie galezie (jesli nie ma konfliktow, dodaje nowy commit)
jesli natomiast sa, musimy je rozwiazac i zrobic commit.
- __git checkout branch_name__ ---> zmienia galaz na branch_name
