# LongSlice
LongSlice, un programma che data una stringa formata solo da cifre e uno "span", permette di calcolare il prodotto più grande per una sua sottostringa contigua di cifre di lunghezza N.

## Descrizione del progretto

Realizzazione di un programma in console che permette di mostrare in output la sequenza di numeri più grande fra tutte quelle presenti.
**Ad esempio:**

- data in ingresso la stringa "1027839564", 
- il prodotto più grande per una serie di 3 cifre è 270 (9 * 5 * 6)
- e il prodotto più grande per una serie di 5 cifre è 7560 (7 * 8 * 3 * 9 * 5).

## Come funziona?
  
<details>
<summary>Controllo dello span</summary>

```c#
    if (span > length){
        throw new System.ArgumentException();
    }
    if (span < 0){
        throw new System.ArgumentException();
    }
    if (span == 0){
        return 1;
    }
```

Questo pezzo di codice serve a verificare che un determinato span che ci arriva non sia minore di 0 o maggiore della lunghezza, in quel caso manda un errore, nel caso invece che lo span sia uguale a 0, a quel punto restituiamo 1
</details>

<details>
<summary>Verificare che la sequenza di numeri non abbia lettere all'interno</summary>

```c#
      for (int i = 0; i < length; i++){
          if(char.IsLetter(vet[i])){
              throw new System.ArgumentException();                
          }
      }
```

Questo pezzo di codice controlla se dentro la stringa che abbiamo ricevuto siano presenti delle lettere, in quel caso lancia un errore
</details>
  
  
<details>
<summary>Calcolo</summary>

```c#
  for (int i = 0; i <= length-span; i++){
              int tmp = i;
              int prodotto = 1;
              for (int x = 0; x < span; x++)
              {
                  prodotto = prodotto * (vet[tmp]-48);
                  tmp += 1;
              }  
              if(maggiore < prodotto)
              {
                  maggiore = prodotto;
              }
          }
          return maggiore;
```

Questo pezzo di codice fa il calcolo richiesto dal problema e restituisce il prodotto più grande
</details>
  
  
  
  
