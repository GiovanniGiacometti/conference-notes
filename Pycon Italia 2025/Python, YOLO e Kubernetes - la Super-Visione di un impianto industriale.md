# Python, YOLO e Kubernetes - la Super-Visione di un impianto industriale

https://2025.pycon.it/en/event/python-yolo-e-kubernetes-la-super-visione-di-un-impianto-industriale

Speaker: [Michele Zanchi](https://www.linkedin.com/in/michele-zanchi-907411168/)

---

Localizzare la punta in un immagine. Se non c'è la punta, bloccare processo.

Tempi strettissimi (il processo avviene ogni 30 secondi)

---

Requisiti:

- requisiti modellistici:
  - dobbiamo evitare falsi positivi
  - minimizzare falsi negativi (tempo è denaro)
  - localizzare la punta (la posizione è importante per capire lo stato)
- requisiti architetturali:
  - <=2 secondi
  - tutto su cpu

1. Modello

YOLO

- state of the art for object detection (both accuracy and speed)
- dataset is small and unbalanced (1/2 times per year the edge is not present)

label studio per etichettare le immagini

fine tuning su 2000 immagini

2. Servizio

Servizio rest basato su flask (devono integrarsi con un sistema scritto in csharp)

endpoint `/classify`

immagine docker slim-buster

deployato on premise sul cluster kubernetes

Concetto chiave `osservability`

2 metriche applicative:
- modello
- processing request time

Password graphana

3. Integrazione

dll in csharp che facesse da client

4. Valutazione

---

Punti di miglioramento:

- evitare dipendenza dalla connettività intercontinentale
- a volte c'erano latenze (fino a 5 minuti al giorno)

-> Spostare il servizio là

- mettere un nodo nel cluster dell'impianto (difficile perché di solito il cluster sta tutto nella stessa region)

Come salvare le metriche?

Thread di python per inviare le metriche in Italia

Di fatto è una classe che gestisce un thread all'interno del quale ci si salva una coda che contiene i payload da inviare

poi c'è una funzione store_data che runna in un while true e invia i dati prendendoli dalla coda

---

Takeaways:

- transfer learning 
- località del modello
- monitoraggio costante
- estendibilità e adattamento continuo


---

Hanno addestrato il modello con le immagini su cui faceva fatica