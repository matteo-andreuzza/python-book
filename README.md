# Basi di python
di Matteo Andreuzza
Derivato da C++ Book -> https://matteo-andreuzza.github.io/cpp-book/
# Le basi di python
## Variabili e costanti
Per contenere dei valori utilizziamo variabili e costanti:
- variabili per contenere un valore che **può variare**
- costanti per contenere un valore che **NON può variare**

Per essere considerata esistente, una variabile o una costante dev'essere **DICHIARATA**:
**Dichiarazione di una variabile:**

```python
raggio = 20;
```
- **Nome:** scelgo un nome a piacere per la variabile
- **Contenuto:** Il contenuto della variabile deve rispettare le condizioni del datatype, ad esempio numeri interi per variabili `int`, numeri con virgola per variabili `float`, valori `True` o `False` per le variabili `bool`, valori di singole lettere per variabili `char`.
> **Nota bene:**
>In Python, il **datatype** di una variabile NON dev'essere dichiarato, in quanto viene riconosciuto automaticamente, a differenza di altri linguaggi dove dev'essere specificato

> **Nota bene:**
>la variabile `bool` accetta SOLO valori `true` e `false`, i quali vanno inserirti rigorosamente in minuscolo. La variabile `bool` va sempre inizializzata

per visualizzare il tipo di una variabile utilizziamo la funzione `tipe()`:
```python
x = 15
type(x)


```
```
#output
<class 'int'>
```
## Conversioni di variabili
Le variabili possono essere convertite da un datatype ad un'altro utilizzando gli appositi metodi di python.
```python
#Convertiamo un numero in una stringa:
n = 15
type(n) # <class 'int'>
a = str(n)
type(a) #<class 'str'>
```

 
## Funzioni di base di Python:
Per comunicare con l'utente, il programma utilizza la finestra della conosole dove viene eseguito il programma. Per interagire con l'utente esistono due funzioni, per scrivere sulla finestra e per leggere un dato inserito dall'utente.

**Scrivere sulla console (Stampa a schermo)**
Utilizziamo la funzione `print()` per stampare un messaggio a schermo:
```python
print("Hello World");
```
Per stampare un testo ed un numero possiamo usare una virgola:
```python
n = 5
print("il numero n è: ", n)
```

**Leggere dati inseriti dall'utente:**
Utilizziamo la funzione `input()` per leggere ciò che digita l'utente. Il contenuto verrà memorizzato in una variabile.
```python
a = input("inserire del contenuto")
```

## Operazioni matematiche:
Possiamo compiere semplici operazioni matematiche sfruttando gli operatori presenti in python.
```python
operazione = (34.5+1552) - ((568 * 645) / 4)
```

# Costrutti complessi in python (1)
## Operatori di selezione
### Selezione semplice
Possiamo effettuare delle operazioni di **selezione** di dati o istruzioni. Parangonandola al linguaggio comune, la selezione è l'equivalente di espressioni del tipo:
>_Se accade questo_ [condizione]
   _allora_ [e cosa succede]
   _altrimenti_ [e cosa succede altrimenti]
   
**esempio 1:**
_Se bevi acido cloridrico allora potresti stare male, altrimenti non starai male._
**esempio 2:**
_Se ti metti questo vestito, allora sei bellissima, altrimenti sei bella comunque, anche senza, rimarrai la donna più bella di questo mondo._

Paragoniamo ora il primo esempio ad un codice di programmazione:

<div style="width: 100%;">
	<!-- THE LEFT COLUMN -->
		<div style="width: 48%; float: left; margin-right: 4%;">
			Se bevi acido cloridrico allora potresti stare male, altrimenti non starai male.
		</div>
	<!-- END THE LEFT COLUMN -->
	
	<!-- THE RIGHT COLUMN -->
		<div style="width: 48%; float: left;">
			if bevi_acido_cloridiro : <br>
				print('starai male')<br>
			<br>
			else:<br>
				print('non starai male')<br>
			
		</div>
	<!-- END THE RIGHT COLUMN -->
</div>
Vediamo quindi come costruire un costrutto di selezione:

```python
if condizione:
	# blocco di codice da eseguire se la condizione è vera
else:
	# blocco di codice da eseguire se la condizione risulta falsa
```
La prima parte contiene la parola chiave ```if``` che ordina al computer di **verificare** le condizioni presenti all'interno delle parentesi ed eseguire blocco di codice contenuto nelle parentesi graffe in caso le condizioni siano vere.
La seconda parte contiene la parola chiave ```else``` che ordina al computer di eseguire il blocco di codice contenuto nelle parentesi graffe se la condizione risulta falsa.

Per comprendere meglio, analizziamo il funzionamento del costrutto:
1. Il computer verifica le condizioni all'interno delle parentesi tonde. Una condizone vera è ad esempio 1 == 1, una falsa è ad esempio 1== 2.
> ATTENZIONE!
> Per fare un'operazione di confronto, occorre inserire due simboli di uguale ( == ), in quanto un solo = corrisponde ad un'operazione di ASSEGNAZIONE, ad esempio float a = 2.

2. Se la condizione è VERA, viene eseguito il blocco di codice contenuto nelle parentesi graffe, se è falsa invece, si passa al passo 3.
3. Se la condizione è FALSA, viene eseguito il blocco di codice contenuto nelle parentesi graffe dell'else. 

### Selezione annidata
La selezione annidata è un'estensione della selezione semplice, che consiste nell'inserimento di uno o più if all'interno di un'altro if.
Nel linguaggio comune un'operazione di selezione annidata potrebbe corrispondere ad un'espressione del tipo:
_Se avrò dei figli, se questi avranno dei figli allora sarò nonna, altimenti, se non avranno figli, rimarrò madre, se non avrò figli, rimarrò sola._
Applichiamo una subordinazione grafica alla frase per comprenderla meglio:

_Se avrò dei figli_
	 &#8192 _se questi avranno figli_
	 &#8192&#8192	_sarò nonna
	 &#8192 se non avranno figli_
	 	&#8192&#8192_rimarrò madre
Se non avrò figli
	&#8192rimarrò sola._

Paragoniamo ancora una volta con un linguaggio di programmazione:

<div style="width: 100%;">
	<!-- THE LEFT COLUMN -->
		<div style="width: 48%; float: left; margin-right: 4%;">
			Se avrò dei figli, se questi avranno dei figli allora sarò nonna, altimenti, se non avranno figli, rimarrò madre, se non avrò figli, rimarrò sola.
		</div>
	<!-- END THE LEFT COLUMN -->
	
	<!-- THE RIGHT COLUMN -->
		<div style="width: 48%; float: left;">
			if avrò dei figli: <br>
				elif avranno dei figli: <br>
					print('sarò nonna')<br>
				<br>
				else:<br>
					print('rimarrò madre') <br>
				<br>
			<br>
			else:<br>
				print('rimarrò sola')<br>
			<br>
			<!-- END THE RIGHT COLUMN -->
</div>
</div>
Vediamo quindi come costruire un costrutto di selezione annidata:

``` python
if condizione:
	if condizione2:
		# blocco di codice da eseguire se la condizione2 è vera
	else:
		# blocco di codice da eseguire se la condizione2 risulta falsa
	
	# blocco di codice da eseguire se la condizione è vera
else:
	# blocco di codice da eseguire se la condizione risulta falsa
```
Un secondo if si può inserire anche nell'else:

``` python
if condizione:
	# blocco di codice da eseguire se la condizione è vera
else:
	if cndizione2:
		# blocco di codice da eseguire se la condizione2 è vera
	else:
		# blocco di codice da eseguire se la condizione2 risulta falsa
		
	# blocco di codice da eseguire se la condizione risulta falsa

```

## Gli operatori logici
Come in logica e matematica, anche nell'informatica esistono 3 operatori logici. 
- Or (o questo o quello)
- And (e)
- Not (non)
I loro corrispettivi in linguaggio di programmazione:
- ```or```
- ```and```
- ```!=```
Facciamo degli esempi di comparazione tra proposizioni logiche e in linguaggio di programmazione:
_Se queste mele pesano meno di 7 o più 10 le compro._

``` python
peso_mele = 0
if peso_mele < 7 or peso mele < 10:
	print("peso le mele")
}
```
_Se queste palle da basket sono rosse e gialle, le compro._
_(Tengo rosso come R e giallo come G)_

```python
colore_palle = input("inserire una lettera maiuscola")
colore_palle2 = input("inserire una lettera maiuscola")
if(colore palle == 'G' and colore_palle2 == 'R'){
	print("compro le palle")
}
```



# Cicli in python
In python, come in ogni altro linguaggio di programmazione, i cicli sono dei costrutti che servono a ripetere delle istruzioni per un numero di volte, in base alla veridicità di una condizione.
## Ciclo While
Il ciclo While si presenta come il ciclo più semplice. Il suo scopo è quello di ripetere un blocco di codice se una determinata condizione è vera. Quando questa diventerà falsa, il blocco di istruzioni non verrà più eseguito, ed il programma uscirà dal ciclo. 

>_fino a quando questo è vero_ [condizione]
   _esegui [e cosa succede]

Vediamo quindi come inserire nel codice un ciclo while e la sua sintassi:

``` python
while condizione:
	istruzione1
	istruzione2
	ecc
```

Facciamo un esempio pratico:

``` python
a = 5

while a > 0:
	print("Il ciclo è in funzione, siamo al giro numero", a)
	a = a +1

```

output:

``` shell
Il ciclo è in funzione. Giro numero 0
Il ciclo è in funzione. Giro numero 1
Il ciclo è in funzione. Giro numero 2
Il ciclo è in funzione. Giro numero 3
Il ciclo è in funzione. Giro numero 4
Il ciclo è in funzione. Giro numero 5
Il ciclo è in funzione. Giro numero 6
Il ciclo è in funzione. Giro numero 7
Il ciclo è in funzione. Giro numero 8
Il ciclo è in funzione. Giro numero 9
```

Notiamo che dopo aver completato il decimo ciclo, il programma è uscito dal ciclo, non eseguendo più le istruzioni contenute nelle parentesi graffe.
Per verificare questo avvenimento, inseriamo un print dopo il ciclo, per vedere quando il ciclo sarà terminato.
``` python
a = 5

while a > 0:
	print("Il ciclo è in funzione, siamo al giro numero", a)
	a = a +1

print("Il programma è uscito dal ciclo")
```

output:

``` shell
Il ciclo è in funzione. Giro numero 0
Il ciclo è in funzione. Giro numero 1
Il ciclo è in funzione. Giro numero 2
Il ciclo è in funzione. Giro numero 3
Il ciclo è in funzione. Giro numero 4
Il ciclo è in funzione. Giro numero 5
Il ciclo è in funzione. Giro numero 6
Il ciclo è in funzione. Giro numero 7
Il ciclo è in funzione. Giro numero 8
Il ciclo è in funzione. Giro numero 9
Il programma è uscito dal ciclo
```

Visto? Appena il programma esce dal ciclo, esso esegue le istruzioni che compaiono successivamente.
 
 >**NOTA BENE | valore della variabile:**
 >	Come puoi vedere, il valore della variabile nell'ultimo giro è 9, non 10, eppure il ciclo ha compiuto 10 giri.
 >	Questo è una conseguenza del fatto che in informatica i numeri partono dallo 0, e non da 1.
 >	Questo ci tornerà molto utile più avanti.
 

## Ciclo For
Il ciclo for è un ciclo più complesso del ciclo while, e permette di ripetere un blocco di istruzioni un determinato numero di volte. Come per il While, per eseguire il blocco di codice dovrà essere soddisfatta una condizione.
>per questo numero di volte
   _esegui [e cosa succede]

Vediamo quindi come inserire nel codice un ciclo for e la sua sintassi:

``` python
for i in range(val1, val2):
	istruzione1
	istruzione2
	ecc
```

Come possiamo notare, nell'intestazione troviamo più parole chiave:
`for`: identifica il tipo di ciclo
`i`: crea una variabile di nome `i` con valore  = 0
`in`: dentro a 
`range`: è una funzione di Python che restituisce un elenco di numeri tra un numero di inizio e un numero di fine. 

> Fino a qui può essere difficile capire, niente panico, ora lo spiegheremo meglio:

Il ciclo for crea una variabile `i` con valore `0` e per tante volte quanti sono i numeri che la funzione `range` restituisce, fa girare il ciclo. Ad ogni giro la variabile `i` aumenterà di un numero, in questo modo quando raggiungerà il valore uguale al numero di numeri generati da `range`, fermerà il ciclo.

Vediamo un esempio pratico:

``` python
for i in range(0, 10):
    print("questo è il giro numero ", i)
```

output:

``` shell
Questo è il giro numero0
Questo è il giro numero1
Questo è il giro numero2
Questo è il giro numero3
Questo è il giro numero4
Questo è il giro numero5
Questo è il giro numero6
Questo è il giro numero7
Questo è il giro numero8
Questo è il giro numero9

```

Il ciclo stampa a schermo 10 volte la scritta, scrivendo alla fine il numero del giro.
> Chiariamo che questo è un uso estremamente riduttivo del ciclo for, tanto che questo risultato si potrebbe ottenere anche con un ciclo while.
> Ci limitiamo però a questi esempi, dato che un uso intensivo del ciclo for verrà fatto più avanti.

Tuttavia questa sintassi estremamente semplice del ciclo `for` di Python, ci permette di portare i cicli `for` ad un altissimo livello, dandogli in pasto anche parole intere.
```python
for x in "ALPHANUMERIC":
   print x
```

```shell
A
L
P
H
A
N
U
M
E
R
I
C
```

>**NOTA BENE**
>Abbiamo usato una parola che è stata stampata in più iterazioni. Python l'ha trattata come un normalissimo dato.


### L'albero di asterischi
Programmiamo la parte sinistra:
```python
a = 5
for i in range(a): #per ogni riga
    for k in range(i): #metti un numero di asterischi uguale al numero di riga
        print("*", end="")
    
    print(" ")

```

```shell
* 
** 
*** 
**** 
```

ora la parte destra:
```python
a = 5
for i in range(a):
    for j in range(a,i,-1): # aggiungiamo lo spazio dal bordo
        print(" ", end="")

    for j in range(i):
        print("*", end="")

    print(" ")


```

```shell   
    * 
   ** 
  *** 
 **** 
```
Creiamo un programma che con dei cicli for disegni l'albero degli asterischi:
```python
a = 5
for i in range(a): #ciclo principale, gestisce le righe dell'albero
    for j in range(a,i,-1): #questo ciclo mette gli spazi tra il bordo e l'albero
        print(" ", end="")

    for j in range(i): #questo disegna la parte destra di asterischi
        print("*", end="")

    for k in range(i): # e questo la parte sinistra
        print("*", end="")
    
    print(" ")


```

```shell
      
    ** 
   **** 
  ****** 
 ******** 

```

### esercizi:
Crea un programma che visualizzi questo output:
```shell
h
he
hel
hell
hello
hello 
hello w
hello wo
hello wor
hello worl
hello world
```
soluzione: https://onlinegdb.com/qxtTXJAWVW
## Istruzioni utili nei cicli

### istruzione break
l'istruzione break serve a fermare un ciclo in un determinato momento. Questo può essere utile per terminare il ciclo quando una condizione è soddisfatta.
Esempio:
```python
print ("Estraiamo ALPHA da ALPHANUMERIC:")
for x in "ALPHANUMERIC":
   if x == "N":
       break
   print (x)
```
output:
```shell
Estraiamo ALPHA da ALPHANUMERIC:
A
L
P
H
A
```
il ciclo si ferma quando `x` diventa `N`, perché in quel momento è terminata la parola ALPHA.
### Istruzione continue
L'istruzione ```continue``` interrompe l'iterazione del ciclo, facendolo ripartire. Più specificatamente:

> L'istruzione `continue` ha come effetto l'interruzione dell'iterazione corrente. Il controllo di flusso rimane confinato all'interno del ciclo, ma viene reindirizzato all'iterazione successiva in conseguenza di una circostanza inattesa che invalida o rende superflua l'esecuzione di tale iterazione.

esempio:
```python
print("estraiamo le parole da ALPHA_&_NUMERIC:")
for x in "ALPHA_&_NUMERIC":
   if x == "_" or x == "&":
       print (" ")
       continue
   print (x)
```

output
```shell
estraiamo le parole da ALPHA_&_NUMERIC:
A
L
P
H
A
 
 
 
N
U
M
E
R
I
C
```

Vediamo ora un esempio numerico per capire meglio.
```python
for i in range (10):
    if i == 4:
        continue #Quando i diventa 4, salta i giro
    print(i)
```

```shell
0
1
2
3
5    <= manca il 4
6
7
8
9
```

Riflettiamo un po'...
A cosa possono servire le funzioni `break` e `continue`? Dopotutto in questi esempi numerici e letterali avremmo potuto cavarcela semplicemente modificando le stringhe o i numeri che davamo al programma. Tuttavia, in programmi più complessi, quando ci troviamo davanti a dati complessi o che possono contenere errori, può essere utile saltare un'iterazione in caso ci fosse qualcosa di sbagliato che non possiamo provare, oppure arrivare a fermare un ciclo in casi delicati.




















<br>
<br>
<br>




















































































Non te l'ho mai detto, non so neanche se abbia senso dirtelo, ma infine.... Te vojo ben ❣️...