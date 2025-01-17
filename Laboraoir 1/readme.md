# 📚 GEO 7630 - Laboratoire 1 : Prise en main des outils

## 🎯 Objectif du laboratoire
- Créer un environnement de travail collaboratif.
- Accéder à une base de données.
- Manipuler des données géospatiales.
- Visualiser ces données dans un SIG.
# 📝 Tâches à réaliser

1. **Créer un compte GitHub**

2. **Créer un nouveau dépôt**

3. **Lancer VSCode**

4. **Cloner le dépôt**

# 🚀 Intégration des données géographiques : CSV, PostgreSQL et QGIS

## 📝 Mon travail

### Étape 1 : Importer le fichier CSV dans FME
- J'ai utilisé **FME** pour importer le fichier CSV contenant les établissements alimentaires de Montréal.
  ![1](https://github.com/user-attachments/assets/bc458423-a810-46a0-bb2f-3e3a075bcd05)

- Voici les actions que j'ai réalisées :
  1. Utiliser un **Reader** pour importer le fichier CSV.

  
     ![3](https://github.com/user-attachments/assets/84adc449-4abd-4b40-912f-f259def092cc)

  
     ![2](https://github.com/user-attachments/assets/07092fb6-7ff8-403f-940b-7e5ca1a0df11)

  3. Sélectionner l'option **web - URL** et copier-coller l'adresse du fichier.

  
     ![5](https://github.com/user-attachments/assets/288818ad-7f5c-4e13-b363-097541f7a4c1)
 
     
     ![4](https://github.com/user-attachments/assets/c5a2d22f-a477-434c-8496-dbfcaf457f17)

  5. Vérifier les données avec l'option **Paramètres** : 4 colonnes sont présentes (Adresse, Latitude, Longitude, autres).
 
     
     ![6](https://github.com/user-attachments/assets/634ad264-4a19-4691-9cb8-25f0edb672c2)


---

### Étape 2 : Injecter les données dans PostgreSQL
1. J'ai configuré un **Writer PostgreSQL** dans FME avec ces paramètres :
   - **Host :** `geo7630h25.cvwywmuc8u6v.us-east-1.rds.amazonaws.com`
   - **Schéma :** `public`
     
2. J'ai ajouté un **Transformer VertexCreator** pour transformer les colonnes `Latitude` et `Longitude` en une géométrie de type point.


![7](https://github.com/user-attachments/assets/482f0335-ef45-4974-94f4-1f289ef78542)



![8](https://github.com/user-attachments/assets/b02fbac4-ac59-4454-a328-1b97815f408d)



   
4. J'ai configuré le Writer pour injecter le fichier CSV en tant que nouvelle table dans PostgreSQL.  
   - Nom de la table : `aliment_naturel`.

     ![9](https://github.com/user-attachments/assets/aba9cd1c-e667-481c-ab18-273aa5018a99)

     

5. J'ai vérifié dans PostgreSQL que :
   - La table a bien été créée.
   - Les géométries sont reconnues correctement.

---

### Étape 3 : Visualiser les données dans QGIS
1. J'ai ouvert QGIS et ajouté une **connexion à ma base PostgreSQL** avec ces paramètres :

![10](https://github.com/user-attachments/assets/3aa463b6-46e1-4df8-a978-1c8dd70cbc8e)



![11](https://github.com/user-attachments/assets/0c76baac-11cf-4473-8c63-02bd71513ec3)



   - **Nom d’hôte :** `geo7630h25.cvwywmuc8u6v.us-east-1.rds.amazonaws.com`
   - **Base de données :** `geo7630h25`
   - **Utilisateur :** Mon utilisateur PostgreSQL(Code Permanat).
   - **Mot de passe :** Mon mot de passe PostgreSQL.

     ![12](https://github.com/user-attachments/assets/bf8da084-85d0-4795-bd42-cacdfc71dc2f)

     

3. J'ai appliqué un style à la couche pour rendre les points visibles et compréhensibles (taille, couleur, etc.).
4. J'ai sauvegardé ce style directement dans la base PostgreSQL.

---

### Étape 4 : Validation
- J'ai vérifié que les points étaient positionnés correctement sur la carte selon les coordonnées lat/long fournies.

  
![13](https://github.com/user-attachments/assets/e7805dfa-ed93-47c2-9db8-955d054de1d8)



![14](https://github.com/user-attachments/assets/8467626a-661b-45b4-8166-3eebc333872c)


---



