Bilan de notre TP de Stéganographie LSB

Ce projet de stéganographie nous a permis de tester la technique de steganographie du LSB (Least Significant Bit) pour cacher un message texte dans une image PNG en utilisant uniquement le canal Rouge. Le principe est simple : modifier le dernier bit de la valeur de couleur de chaque pixel sans que l'œil humain ne s'en aperçoive. On a choisis le rouge pour simplifier la matrice d'origine.

La complexité majeur de Python réside dans la manipulation directe des bits:

    L'opérateur ET binaire est crucial pour l'extraction du bit caché et pour l'étape de masquage.

    L'opérateur NON binaire est utilisé pour créer le masque, notamment dans l'expression complexe mais essentielle r = (r & ~1) | bit_to_encode. Cette formule permet de forcer le LSB à zéro avant d'y insérer le nouveau bit.

    L'opérateur OU binaire sert à l'insertion finale du bit de message.

Pour un débutant en Python, ces opérateurs logiques peuvent paraître inhabituels, car ils sont rarement utilisés dans la programmation quotidienne.

En réussissant à encoder et décoder le message grâce à ces opérations binaires, et en utilisant un terminateur ('00000000') pour marquer la fin du message, nous avons démontré que la stéganographie LSB est simple et efficace pour l'occultation.

Il faut absolument utiliser du png sinon ca ne marche pas.
