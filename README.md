# test_markdown


## Description textuelle (détaillée) du protocole ##

1. L'agent A envoie le message suivant au serveur: m1 = < A, enc( K, K_as ), enc ( B, K_as ) >
2. Le serveur reçoit ce message et tente d'en déchiffrer les parties m[1] et m[2] grâce à la clef K_{m[0]}. En cas d'échec, le protocole s'arrête.
Notons :
- K_{m[0]} = K_1,
- dec( m[1] , K_1 ) = clear_m1[1]
- dec( m[2] , K_1 ) = clear_m1[2]<br>
Le serveur émet alors le message suivant : m2 = < m1[0], clear_m1[2], enc ( clear_m1[1], K_{clear_m1[2]}) ) > (si tout se passe comme prévu, m2 = < A, B, enc ( K, K_bs ) >))

3. Une fois ce message décodé par B, B renvoie m3 = < m2[0], enc( B, dec( m2[2], K_bs ) ) > = < A, enc ( B, K ) >

----
