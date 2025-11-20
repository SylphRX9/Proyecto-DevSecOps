# PASO 1 BUILDER (ESTO PARA OPTIMIZAR LA IMAGEN FINAL)

FROM python:3.11-slim AS builder

WORKDIR /instalacion

COPY requisitos.txt .

RUN pip install --no-cache-dir -r requisitos.txt && rm -rf /root/.cache/pip

# PASO 2 CONSTRUCCION IMAGEN FINAL (AQUI SE UTILIZA SOLO LO NECESARIO PARA QUE FUNCIONE LA API EXCLUYENDO COMPILADORES etc.)

FROM python:3.11-slim

WORKDIR /Aplicacion

COPY --from=builder /usr/local/lib/python3.11/site-packages /usr/local/lib/python3.11/site-packages

COPY --from=builder /usr/local/bin/ /usr/local/bin/

COPY . .

CMD ["gunicorn","-b","0.0.0.0:1025","Servidor:app"]