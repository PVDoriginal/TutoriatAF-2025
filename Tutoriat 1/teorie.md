## Noduri / Muchii Critice 

  - O muchie critica este o muchie pe care, daca o eliminam, graful nu mai este conex (se sparge in mai multe bucati).
  - Similar, un noc este critic daca atunci cand il eliminam, cu tot cu muchiile sale, rezulta un graf care nu e conex.

De exemplu, pentru graful: 

<img width="300" alt="image" src="https://github.com/user-attachments/assets/5072bd95-12c0-4a3b-84a6-28643dd5c3dd" />

Un nod critic este 8. 
Putem observa ca graful se separat in 2 componente conexe daca il stergem:
<img width="300" alt="image" src="https://github.com/user-attachments/assets/6cca3db5-78d0-4387-80e5-6f6a2000bedc" />

Iar o muchie critica este 7-8 (muchia dintre 7 si 8). 
Daca o stergem, graful se va separa in 2 componente conexe: 

<img width="300" alt="image" src="https://github.com/user-attachments/assets/8708e8c0-c259-427f-887b-ed10f87cc883" />

(Observatie: 7 *NU* este nod critic, pentru ca, daca il stergem, graful va ramane o singura componenta conexa formata din celelalte noduri) 

## [DFS](https://en.wikipedia.org/wiki/Depth-first_search) 

Intr-o parcurgere DFS vom porni dintr-un nod precizat, si ne vom duce la fiecare pas la un vecin nevizitat. Daca nodul in care suntem nu mai are vecinit nevizitati, ne intoarcem inapoi in parcurgere pana gasim un astfel de nod.

Puteti vedea un exemplu de DFS [aici](https://www.cs.usfca.edu/~galles/visualization/DFS.html).

## [BFS](https://en.wikipedia.org/wiki/Breadth-first_search) 

Intr-o parcurgere BFS vom porni dintr-un nod vizitat, il vom pune intr-o coada, iar la fiecare pas scoatem un nod din coade si ii adaugam toti vecinii nevizitati. 
Aceasta parcurgere ne da o idee despre distanta dintre noduri intr-un graf neponderat.

Puteti vedea un exemplu de BFS [aici](https://www.cs.usfca.edu/~galles/visualization/BFS.html).

## Observatie - Parcurgere Lexicografica

Chiar daca nu este necesar in practica, la examen sunteti nevoiti sa parcurgeti nodurile in ordine [lexicografica](https://en.wikipedia.org/wiki/Lexicographic_order). Adica, daca sunteti in nodul 5 care are vecini pe 7, 1, 9. Veti alege mereu urmatorul nod din parcurgere ca fiind cel mai mic dintre cele nevizitate (mai intai 1, dupa 7, dupa 9). 

Unii profesori vor asta pentru a putea corecta mai repede examenele (exista mai multe parcurgeri bfs / dfs corecte, dar doar una care sa fie si lexicografica). 

## [Grafuri Bipartite](https://en.wikipedia.org/wiki/Bipartite_graph)
Un graf bipartit este un graf in care nodurile pot fi separate in 2 categorii, iar fiecare muchie uneste doar noduri din categorii diferite (nu exista muchie de la un nod din categoria 1 la alt nod din categoria 1). 

<img width="250" height="124" alt="image" src="https://github.com/user-attachments/assets/c8a04c22-067e-428e-9968-e565815c0517" />

O metoda simpla si folosita frecvent de a determina daca un graf este bipartit, este de a face o parcurgere (de obicei dfs) dintr-un nod pe care-l marcam cu 0 sau 1, iar la fiecare pas, vom marca vecinii nodului in care suntem cu cealalta cifra (daca acum suntem intr-un nod marcat cu 0, toti vecinii trebuie sa fie marcati 1).

Astfel, determinam bipartitia nodurilor, iar daca ajungem intr-o stare in care un nod este marcat cu 0 si are un vecin deja vizitat marcat tot cu 0 (respectiv ambele cu 1), graful nu este bipartit si ne putem opri.

Ne putem imagina 0 si 1 ca fiind si culori, algoritmul rezultand in ceva de forma asta (daca graful este bipartit): 
<img width="250" height="64" alt="image" src="https://github.com/user-attachments/assets/6dc05714-4dc9-42f9-9499-c073bd351773" />
