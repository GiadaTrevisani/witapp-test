# witapp-test

## Installazione

### Requirements

I requisiti sono avere Python versione >= 3.6

Per un installazione di sviluppo installare i requirements da `requirements_dev.txt`.
Per un installazione in produzione, installare `requirements.txt`.

```bash
pip install -r requirements.txt
```

### Setup progetto

Per comodità il database in formato sqlite è stato committato e quindi non è necessario applicare migrazioni o altro.

L'utente superadmin creato è il seguente:

```text
admin
admin1234
```

## Lanciare progetto

Per lanciare il progetto in modalità sviluppo:

```bash
cd mysite
python manage.py runserver
```

Per deployare il progetto in produzione sarebbe necessario invece uno strumento come `gunicorn` e inoltre sarebbe necessario impostare le seguenti variabili d'ambiente:

```bash
DEBUG=false
SECRET_KEY='SUPER-SECRET-KEY'
```

## Sviluppo

Se durante lo sviluppo è necessario aggiungere dei requirements, inserirli nel file `.in` appropriato e poi compilare i requirements con il seguente comando nella root:

```bash
pip-compile requirements_dev.in # use requirements.in for production
```

prima di committare il codice usare il code linter:

```bash
black .
```
