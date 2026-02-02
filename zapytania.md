# Zadanie 1

```sql
SELECT k.tytul AS Tytul, d.dziedzina AS Dziedzina FROM ksiazki k INNER JOIN dziedziny d on k.dziedzina=d.id_dziedziny
```

# Zadanie 2
```sql
SELECT DISTINCT w.nazwawydawnictwa AS Wydawnictwo FROM ksiazki k inner join wydawnictwa w on k.wydawnictwo=w.id_wydawictwa WHERE k.rokwydania LIKE "197*"
```

# Zadanie 3

```sql
SELECT d.dziedzina AS Dziedzina FROM dziedziny d LEFT JOIN ksiazki k ON d.id_dziedziny = k.dziedzina WHERE k.dziedzina IS NULL
```

# Zadanie 4

```sql
SELECT c.imie AS Imie, c.nazwisko AS Nazwisko, Count(*) AS Ilość FROM czytelnicy c INNER JOIN wypozyczenia w ON c.id_czytelnika = w.id_czytelnika GROUP BY c.imie, c.nazwisko
```

# Zadanie 5

```sql
SELECT TOP 1 k.tytul, COUNT(*) AS liczba_wypozyczen FROM (ksiazki AS k INNER JOIN egzemplarze AS e ON k.isbn = e.isbn) INNER JOIN wypozyczenia AS w ON e.sygnatura = w.sygnatura GROUP BY k.tytul ORDER BY COUNT(*) DESC;
```

# Zadanie 6
```sql
SELECT DISTINCT c.imie AS Imie, c.nazwisko AS Nazwisko FROM (czytelnicy c INNER JOIN wypozyczenia w ON c.id_czytelnika = w.id_czytelnika) INNER JOIN Pracownicy p ON w.pracownik = p.IdPracownika WHERE p.NazwiskoPracownika = 'POLO';
```

# Zadanie 7
```sql
SELECT DISTINCT w.sygnatura AS Sygnatura FROM wypozyczenia w WHERE w.datazwrotu IS NULL;
```

# Zadanie 8
```sql
SELECT DISTINCT k.tytul AS Tytuł FROM (ksiazki k LEFT JOIN egzemplarze e ON k.isbn = e.isbn) LEFT JOIN wypozyczenia w ON e.sygnatura = w.sygnatura WHERE w.sygnatura IS NULL;
```

# Zadanie 9
```sql
SELECT k.tytul AS Tytuł FROM ksiazki k INNER JOIN egzemplarze e ON k.isbn = e.isbn GROUP BY k.tytul HAVING COUNT(e.sygnatura) = 1;
```

# Zadanie 10
```sql
SELECT j.nazwajezyka AS Język FROM jezyki j LEFT JOIN ksiazki k ON j.id_jezyka = k.jezykorg WHERE k.isbn IS NULL;
```

# Zadanie 11
```sql
SELECT COUNT(*) AS Wypozyczenia_bez_pracownika FROM wypozyczenia WHERE pracownik IS NULL;
```
