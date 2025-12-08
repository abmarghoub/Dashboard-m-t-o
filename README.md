# TP 2 : Dashboard météo en temps réel avec WebSocket (Node.js + CSV + Chart.js)
## 1. Objectif du TP

L’objectif de ce TP est de développer une application web permettant :

* de **lire un fichier CSV** contenant des données météorologiques,
* d’envoyer ces données **en temps réel** au client via un **serveur WebSocket**,
* d’afficher les valeurs reçues dans :
  un **tableau HTML**,
  un **graphique de températures** (max/min),
  un **graphique des jours de pluie**,
* d’ajouter des fonctionnalités : **Pause/Reprendre** et **Reset** côté client.


---

## 2. Architecture du TP

L’application se compose de trois couches principales :

1. **Serveur Node.js**

   * Lit le fichier `temp.csv`
   * Convertit les lignes grâce à `csvtojson`
   * Envoie chaque ligne au client via `ws` (WebSocket)

2. **Client Web (HTML + JS)**

   * Se connecte au serveur via WebSocket
   * Affiche les données dans un tableau HTML
   * Met à jour deux graphiques Chart.js en temps réel
   * Gère Pause/Reprendre et Reset

3. **Fichier CSV**

   * Contient les données météo (mois, températures, pluie)
   * Doit être au même niveau que `index.js`

---

### **2.1 Stack technologique**

| Technologie             | Rôle                                        |
| ----------------------- | ------------------------------------------- |
| **Node.js**             | Exécution du serveur et lecture du CSV      |
| **ws**                  | Création du serveur WebSocket               |
| **csvtojson**           | Conversion des lignes CSV en objets JSON    |
| **Chart.js**            | Génération des graphiques côté client       |
| **HTML/CSS/JS**         | Interface utilisateur                       |
| **Nodemon** | Redémarrage automatique du serveur          |

---

### **2.2 Structure du projet**

<img width="762" height="428" alt="image" src="https://github.com/user-attachments/assets/e0c86d1c-b046-41ef-a5c9-8788f8da32c6" />

---

## **3. Résultat attendu**

Lorsque le serveur WebSocket est lancé et que la page `index.html` est ouverte dans un navigateur :

