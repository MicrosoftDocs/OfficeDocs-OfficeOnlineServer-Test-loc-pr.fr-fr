---
title: Planification d'Office Web Apps Server
TOCTitle: Planification d'Office Web Apps Server
ms:assetid: 2e147f11-6f47-46bc-90bf-b2f179958d11
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ219435(v=office.15)
ms:contentKeyID: 49645192
ms.date: 02/08/2018
mtps_version: v=office.15
ms.translationtype: MT
---

# Planification d'Office Web Apps Server

 

_**Sapplique à :**Office Web Apps Server_

_**Dernière rubrique modifiée :**2017-10-10_

**Résumé** : Découvrez la configuration requise d’Office Web Apps Server, telle que le protocole HTTPS, les certificats, la virtualisation, l’équilibrage de la charge, les topologies et la sécurité.

**Public concerné** : professionnels de l'informatique

Office Web Apps Server offre des versions des applications Office basées sur le navigateur dans un environnement local, fournissant ainsi aux utilisateurs plus de flexibilité et des possibilités de collaboration. Cet article décrit la configuration requise et les étapes à suivre pour installer Office Web Apps Server dans votre organisation.

Il est important de planifier avec soin afin que tous les hôtes, tels que SharePoint 2013 et Lync Server 2013, peuvent communiquer avec le Office Web Apps Server. Pour plus d’informations sur la configuration des hôtes, consultez les ressources suivantes :

  - [Planification d'Office Web Apps (utilisé avec SharePoint 2013)](plan-office-web-apps-used-with-sharepoint-2013.md)

  - [Déploiement d’Office Web Apps Server et de Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=256902)

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219459.note(Office.15).gif" title="Remarque" alt="Remarque" /> <strong>Remarque :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Produits SharePoint 2010 ne peut pas être un hôte pour Office Web Apps Server. Office Web Apps Server n’est pas pris en charge par SharePoint Foundation 2010 ou SharePoint Server 2010. Office Web Apps Server n’est pas également pris en charge par Exchange Server 2013.</td>
</tr>
</tbody>
</table>


Contenu de cet article :

  - Configuration logicielle et matérielle requise pour Office Web Apps Server

  - Prise en charge de la virtualisation d'Office Web Apps Server

  - Configuration requise du pare-feu pour Office Web Apps Server

  - Configuration requise en matière d'équilibrage de charge pour Office Web Apps Server

  - Configuration DNS requise pour Office Web Apps Server

  - Planification des modules linguistiques pour Office Web Apps Server

  - Planification de la topologie pour Office Web Apps Server

  - Planification de la sécurité pour Office Web Apps Server

  - Planification des visionneuses en ligne avec Office Web Apps Server

  - Planification des mises à jour pour Office Web Apps Server

## Configuration logicielle et matérielle requise pour Office Web Apps Server

Vous pouvez installer Office Web Apps Server en tant que batterie Office Web Apps Server à un seul serveur ou en tant que batterie Office Web Apps Server multiserveur à charge équilibrée. Vous pouvez utiliser des serveurs physiques ou des instances d’ordinateur virtuel, mais vous ne pouvez pas installer d’autres applications de serveur (telles que SharePoint 2013 ou SQL Server) sur le même serveur qu’Office Web Apps Server.

Dans les environnements qui contiennent des données utilisateur réelles, nous vous conseillons toujours d’utiliser le protocole HTTPS, pour lequel vous devez obtenir un certificat. Si vous utilisez plusieurs serveurs dans votre batterie, vous devrez configurer une solution d’équilibrage de la charge logicielle ou matérielle. Pour en savoir plus sur ces scénarios, consultez les sections suivantes.

## Configuration matérielle requise pour Office Web Apps Server

Office Web Apps Server utilise la même configuration matérielle minimale que SharePoint Server 2013. Vous pouvez trouver l’intégralité de la configuration requise de SharePoint 2013 dans la rubrique [Configuration matérielle requise : installations de serveurs web, serveurs d'applications et serveurs uniques](https://technet.microsoft.com/fr-fr/4d88c402-24f2-449b-86a6-6e7afcfec0cd\(office.15\)#hwforwebserver).

## Systèmes d'exploitation pris en charge pour Office Web Apps Server

Vous pouvez exécuter Office Web Apps Server sur les systèmes d’exploitation suivants :

  - L’Édition 64 bits de Windows Server 2008 R2 Service Pack 1 (SP1) Standard, Enterprise ou Datacenter avec la [mise à jour pour Windows Server 2008 R2 x64 édition](https://go.microsoft.com/fwlink/p/?linkid=236954) installé

  - L’édition 64 bits de Windows Server 2012 Standard ou Datacenter

  - L’édition 64 bits de Windows Server 2012 R2. Pour utiliser ce système d’exploitation, vous devez utiliser Office Web Apps Server Service Pack 1 (SP1).

## Conditions requises en matière de domaine pour Office Web Apps Server

Tous les serveurs de la batterie Office Web Apps Server doivent être membres d’un domaine. Ils peuvent faire partie d’un même domaine (recommandé) ou de plusieurs domaines dans la même forêt. Cependant, Office Web Apps Server ne fonctionnera pas si vous essayez de l’installer sur un contrôleur de domaine.

## Rôles serveur, services et autres logiciels requis pour Office Web Apps Server

Tout d’abord, voici quelques actions que vous ne devez PAS effectuer lors du déploiement d’Office Web Apps Server.

  - **N’installez aucune autre application serveur sur le serveur qui exécute Office Web Apps Server**. Ceci inclut Exchange Server, SharePoint Server, Lync Server et SQL Server. Si vous manquez de serveurs, envisagez d’exécuter Office Web Apps Server dans une instance d’ordinateur virtuel sur l’un de vos serveurs.

  - **N’installez aucun service ou rôle dépendant du rôle Serveur web (IIS) sur le port 80, 443 ou 809**, car Office Web Apps Server supprime régulièrement les applications web sur ces ports.

  - **N’installez aucune version d’Office**. Si Office est déjà installé, vous devez le désinstaller pour installer Office Web Apps Server.

  - **N’installez pas Office Web Apps Server sur un contrôleur de domaine**. Il ne s’exécute pas sur un serveur avec les services de domaine Active Directory (AD DS).

Maintenant, voici les éléments que vous DEVEZ installer. Pour plus de détails, voir le tableau suivant.

<table>
<thead>
<tr class="header">
<th><img src="images/Ff431682.important(Office.15).gif" title="Important" alt="Important" /> <strong>Important :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Office Web Apps Server est uniquement disponible pour téléchargement à partir du <a href="https://go.microsoft.com/fwlink/p/?linkid=256561">Volume Licensing Service Center de gestion des</a>. Pour télécharger Office Web Apps Server, vous devez posséder une licence, sous contrat de licence en Volume, Office Professionnel Plus 2013, Office Standard 2013 ou Office pour Mac 2011. Le téléchargement se trouve dans Office sur le portail de gestion des produits.</td>
</tr>
</tbody>
</table>


### Téléchargements, rôles serveur et fonctionnalités obligatoires pour Office Web Apps Server

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Téléchargement, rôle serveur ou fonctionnalité</th>
<th>Pour une installation sur Windows Server 2008 R2</th>
<th>Pour une installation sur Windows Server 2012</th>
<th>Pour une installation sur Windows Server 2012 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Téléchargement</strong> : Office Web Apps Server</p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=256561">Serveur de Office Web Apps</a></p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=256561">Serveur de Office Web Apps</a></p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=256561">Serveur de Office Web Apps</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Téléchargement</strong> : Office Web Apps Server SP1</p></td>
<td><p>Recommandé</p></td>
<td><p>Recommandé</p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=510097">Office Web Apps Server SP1</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Téléchargement</strong> : version correcte de .NET Framework</p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=256560">.NET Framework 4.5</a></p></td>
<td><p>.NET framework 4.5 est déjà installé</p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=510096">.NET Framework 4.5.2</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Téléchargement</strong> : mise à jour pour Windows Server 2008 R2 Édition x64</p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=236954">Mise à jour pour Windows Server 2008 R2 x64 Edition</a></p></td>
<td><p>Non applicable</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Téléchargement</strong> : Windows PowerShell 3.0</p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=244693">Windows PowerShell 3.0</a></p></td>
<td><p>Déjà installé</p></td>
<td><p>Déjà installé</p></td>
</tr>
<tr class="even">
<td><p><strong>Rôle serveur</strong> : Serveur web (IIS)</p></td>
<td><p>La liste suivante décrit les services de rôle minimum requis pour le rôle <strong>Serveur web (IIS)</strong>.</p>
<p><strong>Fonctionnalités HTTP courantes</strong></p>
<ul>
<li><p>Contenu statique</p></li>
<li><p>Document par défaut</p></li>
</ul>
<p><strong>Développement d'applications</strong></p>
<ul>
<li><p>ASP.NET</p></li>
<li><p>Extensibilité .NET</p></li>
<li><p>Extensions ISAPI</p></li>
<li><p>Filtres ISAPI</p></li>
<li><p>Textes insérés par le serveur (SSI)</p></li>
</ul>
<p><strong>Sécurité</strong></p>
<ul>
<li><p>Authentification Windows</p></li>
<li><p>Filtrage des demandes</p></li>
</ul>
<p><strong>Outils de gestion</strong></p>
<ul>
<li><p>Console de gestion IIS</p></li>
</ul>
<p>Les options suivantes sont conseillées mais ne sont pas obligatoires :</p>
<p><strong>Performances</strong></p>
<ul>
<li><p>Compression du contenu statique</p></li>
<li><p>Compression du contenu dynamique</p></li>
</ul></td>
<td><p>La liste suivante décrit les services de rôle minimum requis pour le rôle <strong>Serveur web (IIS)</strong>.</p>
<p><strong>Outils de gestion</strong></p>
<ul>
<li><p>Console de gestion IIS</p></li>
</ul>
<p><strong>Serveur web</strong></p>
<ul>
<li><p>Fonctionnalités HTTP courantes</p></li>
<li><p>Document par défaut</p></li>
<li><p>Contenu statique</p></li>
</ul>
<p><strong>Sécurité</strong></p>
<ul>
<li><p>Filtrage des demandes</p></li>
<li><p>Authentification Windows</p></li>
</ul>
<p><strong>Développement d’applications</strong></p>
<ul>
<li><p>Extensibilité .NET 4.5</p></li>
<li><p>ASP.NET 4.5</p></li>
<li><p>Extensions ISAPI</p></li>
<li><p>Filtres ISAPI</p></li>
<li><p>Textes insérés par le serveur (SSI)</p></li>
</ul>
<p>Les services suivants sont conseillés mais ne sont pas obligatoires :</p>
<p><strong>Performances</strong></p>
<ul>
<li><p>Compression du contenu statique</p></li>
<li><p>Compression du contenu dynamique</p></li>
</ul></td>
<td><p>La liste suivante décrit les services de rôle minimum requis pour le rôle <strong>Serveur web (IIS)</strong>.</p>
<p><strong>Outils de gestion</strong></p>
<ul>
<li><p>Console de gestion IIS</p></li>
</ul>
<p><strong>Serveur web</strong></p>
<ul>
<li><p>Fonctionnalités HTTP courantes</p></li>
<li><p>Document par défaut</p></li>
<li><p>Contenu statique</p></li>
</ul>
<p><strong>Sécurité</strong></p>
<ul>
<li><p>Filtrage des demandes</p></li>
<li><p>Authentification Windows</p></li>
</ul>
<p><strong>Développement d’applications</strong></p>
<ul>
<li><p>Extensibilité .NET 4.5</p></li>
<li><p>ASP.NET 4.5</p></li>
<li><p>Extensions ISAPI</p></li>
<li><p>Filtres ISAPI</p></li>
<li><p>Textes insérés par le serveur (SSI)</p></li>
</ul>
<p>Les services suivants sont conseillés mais ne sont pas obligatoires :</p>
<p><strong>Performances</strong></p>
<ul>
<li><p>Compression du contenu statique</p></li>
<li><p>Compression du contenu dynamique</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Fonctionnalité</strong> : services de prise en charge de l'écriture manuscrite</p></td>
<td><p><strong>Services de prise en charge de l'écriture manuscrite</strong></p>
<ul>
<li><p>Prise en charge du mode d'entrée manuscrite</p></li>
</ul></td>
<td><p><strong>Services de prise en charge de l'écriture manuscrite</strong></p>
<ul>
<li><p>La prise en charge du mode d’écriture manuscrite n’est pas obligatoire.</p></li>
</ul></td>
<td><p><strong>Services de prise en charge de l’écriture manuscrite</strong></p>
<ul>
<li><p>La prise en charge du mode d’écriture manuscrite n’est pas obligatoire.</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Prise en charge de la virtualisation d'Office Web Apps Server

Office Web Apps Server est totalement pris en charge pendant son déploiement à l’aide de la technologie Windows Server Hyper-V. Si vous prévoyez de virtualiser Office Web Apps Server, procédez comme suit :

  - Installez Office Web Apps Server dans sa propre instance d’ordinateur virtuel. N’installez aucune autre application serveur, par exemple SharePoint 2013, dans cette instance.

  - Vous pouvez installer Office Web Apps Server dans une instance d’ordinateur virtuel hébergée par un serveur exécutant SharePoint 2013.

  - Pour les batteries Office Web Apps Server multiserveur, chaque instance doit se trouver sur un hôte d’ordinateur virtuel distinct de sorte que la batterie Office Web Apps Server reste disponible si l’un des hôtes échoue.

## Configuration requise du pare-feu pour Office Web Apps Server

Les pare-feu peuvent causer des problèmes en bloquant les communications entre le navigateur web, les serveurs exécutant Office Web Apps Server et les serveurs exécutant SharePoint 2013. Ce blocage des communications peut être encore plus gênant si les serveurs se trouvent dans différentes parties d’un réseau.

Assurez-vous que les ports suivants ne sont pas bloqués par des pare-feu sur le serveur qui exécute Office Web Apps Server ou sur le programme d’équilibrage de la charge :

  - Port 443 pour le trafic HTTPS

  - Port 80 pour le trafic HTTP

  - Port 809 pour le trafic privé entre les serveurs exécutant Office Web Apps Server (si vous configurez une batterie multiserveur)

## Configuration requise en matière d'équilibrage de charge pour Office Web Apps Server

Nous vous conseillons d’adopter une solution d’équilibrage de la charge si vous exécutez Office Web Apps Server sur plus de deux serveurs. Vous pouvez utiliser n’importe quelle solution d’équilibrage de la charge. Par exemple, un serveur exécutant le rôle Serveur web (IIS) avec ARR (Application Request Routing). En réalité, vous pouvez utiliser ARR sur l’un des serveurs qui exécute Office Web Apps Server. Si vous ne disposez pas d’une solution d’équilibrage de la charge, voici quelques ressources vous permettant d’utiliser IIS avec ARR :

  - [Routage de la demande d’installation](https://go.microsoft.com/fwlink/?linkid=236955)

  - [Application demander l’aide de routage](https://go.microsoft.com/fwlink/?linkid=236956)

Idéalement, la solution d’équilibrage de la charge que vous choisissez doit prendre en charge les fonctionnalités suivantes :

  - Routage de la couche 7

  - Activation de l'affinité du client ou de l'affinité frontale

  - Activation du déchargement SSL

Si vous utilisez un programme d’équilibrage de la charge, vous devez installer le certificat sur le programme d’équilibrage de la charge comme indiqué dans la rubrique Sécurisation des communications Office Web Apps Server à l'aide du protocole HTTPS dans cet article.

## Configuration DNS requise pour Office Web Apps Server

Dans les environnements qui utilisent le protocole HTTPS et l’équilibrage de la charge, vous devez mettre à jour DNS de sorte à résoudre le nom de domaine complet (FQDN) du certificat en l’adresse IP du serveur exécutant Office Web Apps Server ou en l’adresse IP attribuée au programme d’équilibrage de la charge pour la batterie Office Web Apps Server.

## Planification des modules linguistiques pour Office Web Apps Server

Les modules linguistiques pour Office Web Apps Server 2013 permettent aux utilisateurs d’afficher des fichiers Office web en plusieurs langues à partir des bibliothèques de documents SharePoint 2013, d’Outlook Web App (sous forme d’aperçus des pièces jointes) et de Lync 2013 (sous forme de diffusions PowerPoint). Toutefois, cela dépend des langues configurées sur l’hôte. Pour afficher des fichiers Office web en plusieurs langues à partir des hôtes, les éléments suivants doivent se vérifier :

  - L’hôte (par exemple, SharePoint Server 2013 ou Lync Server 2013 ) est configuré pour exécuter des applications dans des langues supplémentaires. Le processus d’installation et de configuration des modules linguistiques sur l’hôte est indépendant de l’installation d’un module linguistique sur la batterie de Office Web Apps Server.

  - Les langues sont installées et disponibles sur tous les serveurs de la batterie Office Web Apps Server.

Voici où à [télécharger les modules linguistiques pour Office Web Apps Server](https://go.microsoft.com/fwlink/p/?linkid=263945).

## Planification de la topologie pour Office Web Apps Server

Au minimum, une topologie Office Web Apps Server inclura un ordinateur physique ou virtuel exécutant Office Web Apps Server et au moins un hôte (par exemple, un serveur exécutant Lync Server 2013 ou SharePoint 2013 ). Et, bien sûr, vous aurez besoin un client PC ou un périphérique pour se connecter à l’un des hôtes et d’utiliser la fonctionnalité Office Web Apps. Dans cette topologie minimale, vous pouvez ajouter plus d’hôtes et de plus de serveurs de votre batterie de Office Web Apps Server que nécessaire en fonction des besoins de votre organisation.

Voici une liste de recommandations que vous devez garder à l’esprit lorsque votre topologie Office Web Apps Server gagne en complexité.

  - **Planifiez la redondance.** Si vous utilisez des instances d’ordinateur virtuel, veillez à les placer sur des hôtes d’ordinateur virtuel distincts pour éviter la redondance. D’autres instances sur l’hôte peuvent exécuter des applications de serveur, mais vous ne pouvez pas exécuter les autres applications de serveur sur la même instance qu’Office Web Apps Server.

  - **Tenez-vous en à un centre de données.** Les serveurs d’une batterie Office Web Apps Server doivent se trouver dans le même centre de données. Ne les dispersez pas géographiquement. En règle générale, vous n’avez besoin que d’une batterie de serveurs, sauf si vos besoins en sécurité exigent un réseau isolé disposant de sa propre batterie Office Web Apps Server.

  - **Restez au plus proche des hôtes.** La batterie de serveurs Office Web Apps Server ne doit pas nécessairement se trouver dans le même centre de données que les hôtes qu’elle dessert. Toutefois, pour un travail de modification intensif, nous vous conseillons de placer la batterie Office Web Apps Server aussi près des hôtes que possible. Ceci est moins important pour les organisations qui utilisent Office Web Apps principalement pour l’affichage de fichiers Office.

  - **Planifiez vos connexions.** Connectez tous les serveurs dans la batterie Office Web Apps Server uniquement les uns aux autres. Pour les connecter à un réseau plus vaste, utilisez un pare-feu d’équilibrage de la charge de proxy inverse.

  - **Configurez le pare-feu pour les demandes HTTP ou HTTPS.** Assurez-vous que le pare-feu autorise les serveurs exécutant Office Web Apps Server à lancer des demandes HTTP ou HTTPS vers les hôtes.

  - **Planifiez les communications entrantes et sortantes.** Dans un déploiement connecté à Internet, effectuez un routage de toutes les communications sortantes via un périphérique NAT. Dans une batterie de serveurs multiples, gérez toutes les communications entrantes avec un équilibrage de charge.

  - **Assurez-vous que tous les serveurs de la batterie Office Web Apps Server sont joints à un domaine et font partie de la même unité d’organisation.** Utilisez le paramètre **FarmOU** dans la cmdlet [New-OfficeWebAppsFarm](new-officewebappsfarm.md) pour empêcher d’autres serveurs qui ne font pas partie de cette unité d’organisation de rejoindre la batterie de serveurs.

  - **Utilisez le protocole HTTPS pour toutes les demandes entrantes.**

  - **Si vous avez déployé IPsec dans le réseau, utilisez-le pour chiffrer le trafic entre les serveurs.**

  - **Planifiez les fonctionnalités Office qui utilisent Internet.** Si des fonctionnalités telles que les images clipart et les services de traduction sont nécessaires, et si les serveurs de la batterie ne peuvent pas envoyer de demandes vers Internet, un serveur proxy doit être configuré pour la batterie de serveurs Office Web Apps Server. Ainsi, les demandes HTTP vers des sites externes seront autorisées.

## Planification de la sécurité pour Office Web Apps Server

Les informations suivantes présentent des instructions de sécurité pour Office Web Apps Server.

## Sécurisation des communications Office Web Apps Server à l'aide du protocole HTTPS

Office Web Apps Server peuvent communiquer avec SharePoint 2013 et Lync Server 2013 en utilisant le protocole HTTPS. Dans les environnements de production, nous recommandons vivement que vous utilisez le protocole HTTPS. Vous devrez installer un certificat de serveur Internet qui peut être attribué pour le serveur qui exécute Office Web Apps Server (si vous utilisez un seul serveur) ou à l’équilibreur de charge (si vous utilisez plusieurs serveurs qui exécutent des Office Web Apps Server ).

Dans les environnements de test qui contiennent les données utilisateur, vous pouvez utiliser le protocole HTTP pour SharePoint 2013 et ignorer la demande de certificat. Lync Server 2013 prend en charge uniquement le protocole HTTPS.

Les certificats utilisés par Office Web Apps Server doivent satisfaire aux exigences suivantes :

  - Le certificat doit provenir d’une autorité de certification approuvée et inclure le nom de domaine complet (FQDN) de votre batterie Office Web Apps Server dans le champ SAN (Autre nom de l’objet). (Si le nom de domaine complet ne figure pas dans le SAN, le navigateur affichera des avertissements de sécurité ou ne traitera pas la réponse quand vous tenterez d’utiliser le certificat.)

  - Le certificat doit posséder une clé privée exportable. Dans les batteries à un seul serveur, cette option est sélectionnée par défaut quand vous utilisez le composant logiciel enfichable Gestionnaire des Internet Information Services (IIS) pour importer le certificat.

  - Le champ Nom convivial doit être unique au sein du magasin des autorités de certification racine approuvées. Si vous possédez plusieurs certificats qui partagent un champ Nom convivial, la création de la batterie échoue car la cmdlet New-OfficeWebAppsFarm ne saura pas lequel de ces certificats utiliser.

  - Office Web Apps Server ne nécessite aucune extension ou propriété de certificat particulière. Par exemple, les extensions d’utilisation améliorée de la clé (EKU) du client ou du serveur ne sont pas obligatoires.

  - Sur Windows Server 2012 ou Windows Server 2012 R2, vous devez installer la fonctionnalité Windows Communication Foundation (WCF) « Allow HTTP Activation » (Autoriser l’activation HTTP).

Le certificat doit être importé comme suit :

  - **Pour les batteries à un seul serveur** : vous devez importer le certificat directement sur le serveur qui exécute Office Web Apps Server. Ne liez pas le certificat manuellement. La cmdlet New-OfficeWebAppsFarm que vous exécuterez plus tard le fera pour vous. Si vous liez le certificat manuellement, il sera supprimé à chaque redémarrage du serveur.

  - **Pour les batteries de serveurs à charge équilibrée** : si vous déchargez SSL, vous devez importer le certificat sur le programme d’équilibrage de la charge matérielle. Dans le cas contraire, vous devez installer le certificat sur chaque serveur de la batterie Office Web Apps Server.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219459.note(Office.15).gif" title="Remarque" alt="Remarque" /> <strong>Remarque :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>N'utilisez pas de certificats auto-signés, sauf dans les environnements de test non critiques.</td>
</tr>
</tbody>
</table>


Pour plus d’informations sur les certificats, voir [comment obtenir un certificat SSL](https://go.microsoft.com/fwlink/p/?linkid=269700).

## Utilisation du déchargement SSL pour les programmes d'équilibrage de la charge matérielle

Lorsque vous configurez une nouvelle batterie de serveurs Office Web Apps Server, le déchargement SSL est désactivé par défaut. Si vous utilisez un programme d’équilibrage de la charge matérielle, nous vous recommandons d’activer le déchargement SSL afin que chaque serveur Office Web Apps Server de la batterie puisse communiquer avec le programme d’équilibrage de la charge via HTTP. L’activation du déchargement SSL offre également les avantages suivants :

  - Gestion simplifiée des certificats

  - Affinité logicielle améliorée

  - Performances accrues

Lorsque vous utilisez le protocole HTTP, le trafic en provenance du programme d’équilibrage de la charge et en direction des serveurs exécutant Office Web Apps Server n’est pas chiffré. Vous devez donc veiller à ce que le réseau soit sécurisé. L’utilisation d’un sous-réseau privé peut aider à protéger le trafic.

## Restriction des serveurs qui peuvent rejoindre une batterie Office Web Apps Server selon leur appartenance à une unité d'organisation

Vous pouvez empêcher l’accès des serveurs non autorisés à une batterie Office Web Apps Server en créant une unité d’organisation pour ces serveurs, puis en spécifiant le paramètre FarmOU au moment de la création de la batterie. Pour plus d’informations sur le paramètre FarmOU, voir [New-OfficeWebAppsFarm](new-officewebappsfarm.md).

## Restriction de l'accès des hôtes à Office Web Apps Server à l'aide de la liste autorisée

La liste autorisée est une fonctionnalité de sécurité qui empêche les hôtes indésirables de se connecter à une batterie Office Web Apps Server et de l’utiliser pour effectuer des opérations sur les fichiers sans votre consentement. En ajoutant les domaines approuvés à la liste autorisée, vous pouvez limiter les hôtes pour lesquels Office Web Apps Server autorise les demandes d’opérations sur les fichiers, comme l’extraction de fichiers, l’extraction de métadonnées et les modifications de fichiers.

Vous pouvez ajouter des domaines à la liste autorisée après la création de la batterie Office Web Apps Server. Pour plus d’informations sur l’ajout de domaines à la liste autorisée, voir [New-OfficeWebAppsHost](new-officewebappshost.md).

<table>
<thead>
<tr class="header">
<th><img src="images/Ff431682.important(Office.15).gif" title="Important" alt="Important" /> <strong>Important :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Si vous n’ajoutez pas de domaine à la liste autorisée, Office Web Apps Server autorise les demandes de fichiers aux hôtes de n’importe quel domaine. Ne laissez pas cette liste vide si votre batterie Office Web Apps Server est accessible sur Internet. Sinon, tout le monde pourra utiliser votre batterie Office Web Apps Server pour afficher et modifier du contenu.</td>
</tr>
</tbody>
</table>


## Planification des visionneuses en ligne avec Office Web Apps Server

Par défaut, la fonctionnalité de visionneuse en ligne est activée après l’installation d’Office Web Apps Server. Consultez les instructions suivantes si vous prévoyez d’utiliser des visionneuses en ligne dans votre organisation. Dans certains cas, vous pouvez préférer désactiver certaines fonctionnalités des visionneuses en ligne. Ces instructions font référence aux paramètres configurés à l’aide des cmdlets Windows PowerShell[New-OfficeWebAppsFarm](new-officewebappsfarm.md) et [Set-OfficeWebAppsFarm](set-officewebappsfarm.md).

## Considérations relatives à la sécurité des visionneuses en ligne

Les fichiers destinés à être consultés via des visionneuses en ligne dans un navigateur web ne doivent pas demander d’authentification. En d’autres termes, les fichiers doivent être disponibles publiquement, car les visionneuses en ligne ne peuvent pas effectuer d’authentification au moment de l’extraction des fichiers. Nous vous recommandons fortement de limiter l’accès de la batterie Office Web Apps Server utilisée pour les visionneuses en ligne à un intranet ou à Internet, et non aux deux à la fois. En effet, Office Web Apps Server ne fait pas de distinction entre les demandes d’URL intranet et Internet. Si une demande provient d’Internet pour une URL intranet, par exemple, une faille de sécurité peut se produire si un document interne est visualisé.

Pour la même raison, si vous avez configuré Office Web Apps Server pour qu’il ne se connecte qu’à Internet, nous vous conseillons fortement de désactiver la prise en charge UNC dans les visionneuses en ligne. Pour désactiver la prise en charge UNC, définissez le paramètre OpenFromUncEnabled sur False à l’aide de la cmdlet Windows PowerShell[New-OfficeWebAppsFarm](new-officewebappsfarm.md) (pour les nouvelles batteries) ou [Set-OfficeWebAppsFarm](set-officewebappsfarm.md) (pour les batteries existantes).

Par mesure de sécurité supplémentaire, les visionneuses en ligne sont limitées à l’affichage de fichiers Office dont la taille est inférieure ou égale à 10 Mo.

## Options de configuration des visionneuses en ligne

Vous pouvez configurer des visionneuses en ligne à l’aide des paramètres Windows PowerShell suivants dans [New-OfficeWebAppsFarm](new-officewebappsfarm.md) (pour les nouvelles batteries) ou [Set-OfficeWebAppsFarm](set-officewebappsfarm.md) (pour les batteries existantes).

  - **OpenFromUrlEnabled** : active ou désactive les visionneuses en ligne. Ce paramètre contrôle les visionneuses en ligne pour les fichiers qui disposent de chemins d’accès URL et UNC. Par défaut, ce paramètre est défini sur False (désactivé) quand vous créez une batterie Office Web Apps Server.

  - **OpenFromUncEnabled** : lorsque les visionneuses en ligne sont activées (définies sur True par la cmdlet OpenFromUrlEnabled), ce paramètre active ou désactive la capacité des visionneuses en ligne à afficher des fichiers dans des chemins d’accès UNC. Par défaut, ce paramètre est défini sur True, mais vérifiez que la cmdlet OpenFromUrlEnabled est également définie sur True avant d’autoriser l’ouverture des fichiers à partir de chemins d’accès UNC. Comme décrit plus haut, nous vous conseillons de définir ce paramètre sur False si vous avez configuré Office Web Apps Server pour se connecter à Internet.

  - **OpenFromUrlThrottlingEnabled** : limite le nombre de demandes ouvertes à partir d’URL provenant d’un serveur donné dans une période de temps. Les valeurs de limitation par défaut, qui ne sont pas configurables, assurent qu’une batterie Office Web Apps Server ne sature pas un serveur unique en envoyant des demandes selon lesquelles du contenu doit être affiché dans les visionneuses en ligne.

## Planification des mises à jour pour Office Web Apps Server

Avant de déployer Office Web Apps Server, vous devez décider de la manière dont votre organisation va gérer les mises à jour logicielles dans votre batterie Office Web Apps Server. Bien que ces mises à jour contribuent à accroître la sécurité, les performances et la fiabilité d’un serveur, l’installation incorrecte de mises à jour peut entraîner des problèmes au niveau d’Office Web Apps Server.

L’application de mises à jour Office Web Apps Server à l’aide du processus de mise à jour automatique de Microsoft n’est pas prise en charge avec Office Web Apps Server. Les mises à jour d’un serveur Office Web Apps Server doivent être appliquées d’une certaine manière, comme indiqué dans la rubrique [Application de mises à jour logicielles pour Office Web Apps Server](apply-software-updates-to-office-web-apps-server.md). Si des mises à jour Office Web Apps Server sont appliquées automatiquement, les utilisateurs risquent de ne pas pouvoir afficher ou modifier de documents dans Office Web Apps. le cas échéant, vous devrez reconstruire votre batterie Office Web Apps Server.

Nous vous recommandons de gérer les mises à jour à l’aide de Windows Server Update Services (WSUS) ou à l’aide de System Center Gestionnaire de configuration, qui utilise WSUS. WSUS vous permet de gérer entièrement la distribution de mises à jour publiées via Microsoft Update pour chaque serveur de la batterie Office Web Apps Server. Grâce à WSUS, vous pouvez choisir les mises à jour à appliquer automatiquement à la batterie de serveurs et les mises à jour à appliquer manuellement, par exemple, celles destinées à Office Web Apps Server. Pour plus d’informations sur WSUS, voir [Windows Server Update Services](https://go.microsoft.com/fwlink/p/?linkid=294822).

Si vous n’utilisez ni WSUS, ni System Center Gestionnaire de configuration, définissez les mises à jour automatiques de Microsoft sur chaque serveur de la batterie Office Web Apps Server sur **Télécharger automatiquement, mais notifier l’utilisateur pour installer**. Lorsque vous recevez une notification de l’existence d’une mise à jour Office Web Apps Server, suivez les étapes décrites dans la rubrique [Application de mises à jour logicielles pour Office Web Apps Server](apply-software-updates-to-office-web-apps-server.md). Pour appliquer les mises à jour Windows et garder vos serveurs sécurisés, acceptez les mises à jour Windows dès que vous recevez des notifications concernant leur disponibilité.

## Voir aussi


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Vue d'ensemble d'Office Web Apps Server](office-web-apps-server-overview.md)  
[Déployer Office Web Apps Server](deploy-office-web-apps-server.md)  
[Application de mises à jour logicielles pour Office Web Apps Server](apply-software-updates-to-office-web-apps-server.md)  


[Office.com (pour une aide avec Office Web Apps sur votre appareil mobile ou de bureau)](https://go.microsoft.com/fwlink/p/?linkid=266657)  
  

[apply-software-updates-to-office-web-apps-server.md](apply-software-updates-to-office-web-apps-server.md)

