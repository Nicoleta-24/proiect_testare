Baza de date pentru o bibiloteca, avem tablele:
autor - contine lista de autori
editura - contine lista de edituri
carte - lista de carti prezente in biblioteca, are cheie externa la tabela editura(n la 1) si la tabela autor(n la 1)
cititor - lista de cititori inregistrati la biblioteca
fisa_lectura - lista de carti care au fost imprumutate, are are cheie externa la tabela carte(n la 1) si la tabela cititor(n la 1)
