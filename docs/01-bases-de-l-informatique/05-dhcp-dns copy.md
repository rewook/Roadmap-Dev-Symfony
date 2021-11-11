---
sidebar_position: 5
---

# DHCP, DNS, etc

Afin de bien comprendre les différents services qui gravitent dans l'univers des réseau il est important de faire une analogie avec la distribution du courrier.
Quand nous souhaitons envoyer un gros colis par recommandé nous avons besoins de l'adresse du destinataire et de celle de l'expéditeur. Imaginons que ce colis soit très gros, nous allons préféré envoyé plusieurs petits paquets.

Ces adresses de destinataire et d'expéditeur ont été fixées par l'administration qui détermine des noms de rues et des numéros.Cela rend unique l'adressse d'une personne pour une commune. Pour le réseau informatique ce rôle est appelé DHCP.

**DHCP (Dynamic Host Protocol)**
Lorsque nous démarrons notre ordinateur, celui-ci a besoin d'une adresse IP pour communiquer sur le réseau, d'un masque pour déterminer le réseau auquel il appartient, d'un serveur DNS (que nous verrons plus tard) et d'une passerelle pour pouvoir communiquer avec un réseau extérieur. Si ces informations ne sont pas paramétrés en dur (ou de façon manuelle) un service est chargé de lui attribué une adresse automatiquement. C'est le service DHCP. Il va fournir à notre ordinateur tous les éléments (adresse, masque,passerelle,serveur DNS) dont il a besoin pour échanger avec d'autres ordinateurs ou serveurs.
Ce service est généralement détenu soit par un routeur (ou notre box à la maison), soit par un serveur à qui nous avons configuré le rôle de serveur DHCP.
En plus des informations de masque de sous-réseau, passerelle le technicien réseau va définir une plage d'adresse disponible pour ce service.
Il sera également défini combien de temps sera disponible l'attribution de l'adresse à notre PC, on parle ici de bail. Par exemple, on peut définir un bail de 24h. C'est à dire que si notre pc est éteint plus de 24h, à sa prochaine connexion celui-ci se verra affecté une adresse différente de la précédente.
Tous ces baux sont tenus à jour par les serveur DHCP.
Il est possible sur ce service de définir des adresses qui seront identiques pour une machine données. Prenons l'exemple d'une imprimante, nous souhaitons que son adresse reste identique. Le technicien réseau pourra renseigner l'adresse MAC de l'imprimante dans le serveur DHCP afin que ce dernier lui réserve une adresse IP faisant partie de la plage.

**DNS (Domain Name System)**
Quand nous souhaitons aller sur des sites Internet, par exemple https://fr.wikipedia.org nous renseignons dans notre  navigateur l'adresse du site que nous souhaitons consulté.
Cependant n'oublions pas notre ordinateur communique par le biais de réseau et donc par adresse IP.
Donc en arrière plan un service est chargé de traduire l'adresse du site que nous avons écrit en adresse Ip de destination compréhensible par un ordinateur.
C'est le rôle de DNS. Un serveur très connu est celui de Google qui est accessible à l'adresse IP 8.8.8.8. Sur nos boxs, l'adresse du serveur DNS est souvent liées au fournisseur d'accès Internet (FAI).
Ce service est chargé de tenir à jour une table de correspondance entre les noms de site et leur correspondance en adresse IP.

Si nous reprennons l'exemple où nous souhaitons accéder au site https://fr.wikipedia.org, notre ordinateur va demander à notre Box quelle est l'adresse IP du site wikipedia.
Le serveur DNS de notre FAI va consulter sa table de correspondance. S'il trouve l'adresse, il va communiquer sa réponse à notre box  qui va à son tour communiquer la réponse à notre ordinateur. Notre ordinateur va alors demander la page souhaitée à l'adresse IP qu'il aura reçu.
Si le serveur DNS du FAI ne trouve pas l'adresse dans sa table de correspondance, il va interroger un autre serveur DNS, par exemple Goole.

Une façon de connaitre l'adresse IP d'un site :
![image](https://user-images.githubusercontent.com/24554069/141237779-0dfe45ec-5276-4bb0-bd89-cdbc1ef9fa2f.png)


