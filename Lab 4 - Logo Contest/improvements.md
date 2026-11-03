# L'optimisation des paramètres internes de l'algorithme SIFT (nfeatures, contrastThreshold, edgeThreshold, nOctaveLayers, sigma) est essentielle et a été réalisée par les meilleurs participants via des recherches par grille, aléatoires ou bayésiennes.

# L'adaptation du seuil du test de ratio de Lowe de manière dynamique et spécifique pour chaque logo (généralement entre 0.6 et 0.85), plutôt que l'utilisation d'un seuil global, améliore considérablement le compromis entre précision et rappel.

# Le filtrage des correspondances aberrantes via l'estimation de l'homographie avec l'algorithme RANSAC (cv2.findHomography) est la méthode la plus utilisée pour ne conserver que les inliers géométriquement cohérents.

# L'utilisation de la normalisation RootSIFT à la place du SIFT standard permet d'obtenir des descripteurs plus robustes et stables.

# Le matcher basé sur FLANN (avec KD-tree) est privilégié par rapport à l'approche Brute-Force pour accélérer la recherche des plus proches voisins lors de l'optimisation, tout en conservant une précision similaire.

# Une approche avancée a consisté à appliquer SIFT séparément sur chaque canal d'image (niveaux de gris, rouge, vert, bleu) pour concaténer les résultats dans un vecteur à 512 dimensions.

# Le redimensionnement des images à des résolutions plus élevées (comme 800x800) ou en conservant le ratio d'aspect d'origine permet d'augmenter le nombre de points clés détectés sur les traits fins des logos.

# La normalisation du score final, en divisant le nombre d' inliers par le nombre total de points clés de l'image requête, affine le classement de la base de données.

1. tester valeur lowe ratio treshold avec grid search 0.0->1.0

2. modifier paramètres par défaut de SIFT.create()

3. Modifier la manière de calculer le score des matches

4. Modifier taille des images

5. Ajouter RANSAC

6. valeur de lowe ratio spécifique pour chaque logo