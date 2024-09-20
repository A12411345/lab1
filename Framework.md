**Lucrare de laborator nr. 1.** 

**Bazele HTTP**

**Sarcina nr. 1. Analiza cererilor HTTP**

1. Accesarea site-ul <http://sandbox.usm.md/login>.

Deschiderea filei Network în instrumentele pentru dezvoltatori ale browserului.

1. **Date incorecte pentru autentificare:** username: student, password: studentpass.

![](Aspose.Words.af9e7641-3e44-4144-b74a-b9809d32f45b.001.png)

- **Ce metodă HTTP a fost utilizată pentru a trimite cererea?**

Metoda HTTP utilizată pentru a trimite cererea de autentificare este POST, folosită pentru a trimite date către server.

- **Ce anteturi au fost trimise în cerere?**

connection:keep-alive

content-type:text/plain;charset=UTF-8

date: Thu, 19 Sep 2024 12:40:42 GMT

server:nginx/1.24.0 (Ubuntu)

transfer-encoding:chunked

- **Ce parametri au fost trimiși în cerere?**

username: student password: studentpass

- **Ce cod de stare a fost returnat de server?**

A fost returnat codul de stare 401 Unauthorized \*\*

1. **Date corecte pentru autentificare:** username: admin, password: password.

![](Aspose.Words.af9e7641-3e44-4144-b74a-b9809d32f45b.002.png)

- **Ce metodă HTTP a fost utilizată pentru a trimite cererea?**

Metoda HTTP utilizată pentru a trimite cererea de autentificare este POST.

- **Ce anteturi au fost trimise în cerere?**

Connection: keep-alive

Content-Type: text/plain; charset=UTF-8

Date: Thu, 20 Sep 2024 14:47:59 GMT

Server: nginx/1.24.0 (Ubuntu) Transfer-Encoding: chunked

- **Ce parametri au fost trimiși în cerere?**

username: admin password: password

- **Ce cod de stare a fost returnat de server?**

A fost returnat codul de stare 200 OK \*\*

**Sarcina nr. 2. Crearea cererilor HTTP**

1. **Cererea GET** trimite o solicitare către server la adresa [http://sandbox.com](http://sandbox.com/)

GET / HTTP/1.1

Host: sandbox.com

User-Agent: Bojencu Vitalie

1. **Cererea POST** trimite date către server.

POST /cars HTTP/1.1

Host: sandbox.com

Content-Type: application/x-www-form-urlencoded

make=Toyota&model=Corolla&year=2020

1. **Cererea PUT** este utilizată pentru a actualiza datele pe server.

PUT /cars/1 HTTP/1.1

Host: sandbox.com

User-Agent: Bojencu Vitalie

Content-Type: application/json

{

"make": "Toyota",

"model": "Corolla",

"year": 2021

}

**Cerere POST**

HTTP/1.1 201 Created

Content-Type: application/json

{

"id": 1,

"make": "Toyota",

"model": "Corolla",

"year": 2020

}

**Cerere PUT**

HTTP/1.1 200 OK

Content-Type: application/json

{

"id": 1,

"make": "Toyota",

"model": "Corolla",

"year": 2021

}

**Situații în care serverul poate returna coduri de stare HTTP**

- 200 OK: Cererea a fost procesată cu succes..
- 201 Created: Cererea POST a fost procesată cu succes și a fost creată o nouă resursă.
- 400 Bad Request: Cererea este invalidă, de exemplu, parametrii lipsă sau format incorect.
- 401 Unauthorized: Autentificarea este necesară și a eșuat sau nu a fost furnizată.
- 403 Forbidden: Serverul a înțeles cererea, dar refuză să o autorizeze.
- 404 Not Found: Resursa solicitată nu a fost găsită pe server.
- 500 InternalServer Error: Serverul a întâmpinat o eroare neașteptată care l-a împiedicat să proceseze cererea.
1. **Cererea de tip DELETE** ste utilizată atunci când dorim să eliminăm o resursă de pe server

DELETE /cars/1 HTTP/1.1

Host: sandbox.com

User-Agent: Bojencu Vitalie

