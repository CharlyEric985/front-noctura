NOCTURA — Front relié à Flask

1. Démarrer l’API Flask sur http://127.0.0.1:5000 avec models/noctura_v2.joblib.
2. Placer index.html dans un dossier avec assets/porquerolles-jour.png, assets/porquerolles-crepuscule.png et assets/porquerolles-nuit.png (vos images originales, non incluses).
3. Servir le dossier front avec : python -m http.server 5500
4. Ouvrir http://127.0.0.1:5500
5. Si le navigateur bloque la requête cross-origin, installer flask-cors et ajouter dans app.py : from flask_cors import CORS ; CORS(app, resources={r"/api/*": {"origins": ["http://127.0.0.1:5500", "http://localhost:5500"]}})

L'API est appelée via POST /api/predict. Les niveaux d'éclairage sont uniquement simulés.
La puissance affichée utilise des hypothèses de 2 kW (zone A) et 3 kW (zone B) avec une relation linéaire illustrative.
L'heure et la hauteur solaire sont des entrées indépendantes : pour une démonstration réaliste, utiliser une hauteur solaire calculée pour la date et le lieu.
