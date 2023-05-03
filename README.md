# LONGSLICE

Programma in c per calcolare il prodotto più grande di una sottostringua contigua di lunghezza N in una stringa formata da solo cifre.

## CICLO PRINCIPALE

        for (int j = 0; j <= length-span; j++)
        {
            int prodotto = 1;
            int supp = j;

            for (int x = 0; x < span; x++)
            {
                prodotto = prodotto * (array[supp]-48);
                supp = supp + 1;
            }
                
                if(prodotto > prodottomax)
                {
                    prodottomax = prodotto;
                }
        }

        return prodottomax;
    }

 Il programma dopo aver effettuato i controlli per verificare che il calcolo del prodotto sia possibile controllando sia la lunghezza della sottostringa sia se la stringa principale contiene dei digit, inizia a far girare questo ciclo for che calcolerà tramite l'ausilio di un'altro for annidato ogni sottostringa possibile utilizzando la lunghezza data, quando trova un prodotto maggiore del precendente lo sostituisce a quest'utltimo e a fine ciclo ritorna il prodotto massimo trovato.
 
 ## CONTROLLI PRIMA DEL CICLO
 
         int length = digits.Length;

        if(span > length)
            throw new System.ArgumentException();

        if(span < 0)
            throw new System.ArgumentException();

        if( span==0 )
            return 1;

        
        char[] array = digits.ToCharArray();

        for (int i = 0; i < length; i++)
        {
            if(char.IsLetter(array[i]))
            {
                throw new System.ArgumentException();                
            }
        }
 
