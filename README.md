On veut effectuer en parallèle(En utilisant le modèle producteurs/consommateur) le produit de deux matrices: 
B (n1* m1)  et C (n2 * m2) ⇒ la matrice résultante A=B*C ;

Les matrices sont remplis par des valeurs aléatoires
Markup :  ### q1: Quelles sont les structures de données à utiliser ? ###
Les structures de données utilisées dans ce programme sont principalement des tableaux à deux dimensions (B, C, A) pour représenter les matrices et le tampon T est implémenté comme un tableau unidimensionnel simulant une structure à deux dimensions.

Les résultats intermédiaires seront placés dans un tampon de taille “T[N]”.

Chaque threads producteurs calcule une ligne de la matrice résultante A et range les résultat dans le tampon T
Markup :  ### q2: Comment allez-vous protéger l'accès à ces données? ###
L'accès aux données est protégé par un mutex (pthread_mutex_t mutex) qui assure l'exclusion mutuelle lors de l'accès aux structures de données partagées (T, A) Et deux sémaphores ( full et empty) sont utilisés pour la synchronisation entre les producteurs et les consommateurs, contrôlant l'accès aux emplacements vides et pleins du tampon.
