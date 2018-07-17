---
title: Déployer Office Web Apps Server
TOCTitle: Déployer Office Web Apps Server
ms:assetid: e4d51dc4-6460-437d-aa8e-0ae4d3aa8cc5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ219455(v=office.15)
ms:contentKeyID: 49645245
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Déployer Office Web Apps Server 

_**Sapplique à :**  Office Web Apps Server_

_**Dernière rubrique modifiée :**  2017-10-05_

**Résumé** : Explique comment déployer Office Web Apps Server en local afin de l’utiliser avec SharePoint 2013 et Lync Server 2013.

**Public concerné** : professionnels de l’informatique

Remarque : cet article traite de l’installation de Office Web Apps Server pour votre entreprise. Si vous recherchez de l’aide concernant votre copie personnelle d’Office ou d’Office Web Apps, voir <https://support.office.com>.

Le déploiement d’[Office Web Apps Server](office-web-apps-server-overview.md) implique l’installation de certains logiciels prérequis et l’exécution de quelques commandes Windows PowerShell ; toutefois, dans l’ensemble le processus est conçu pour être relativement simple. Cet article vous explique les procédures à suivre pour préparer vos serveurs, puis vous indique les commandes Windows PowerShell nécessaires pour configurer la batterie de serveurs Office Web Apps Server.

Contenu de cet article :

  - Visionner une vidéo pour voir comment faire

  - Passer en revue ces ressources avant de commencer

  - Préparer des serveurs pour l'exécution d'Office Web Apps Server

  - Déployer la batterie de serveurs Office Web Apps Server

  - En cas d'affichage des messages « Exceptions de service web (500) » ou « Erreur interne du serveur (500.21) »

## Visionner une vidéo pour voir comment faire

Visionnez la vidéo suivante pour voir comment configurer Office Web Apps Server dans un environnement de test. Vous verrez également un aperçu de la configuration de SharePoint 2013 pour utiliser Office Web Apps Server.

**Configurer Office Web Apps Server dans un environnement de test**

> [!VIDEO https://www.microsoft.com/fr-fr/videoplayer/embed/179bf96f-09e1-407a-bb1b-a8e6623eabae]

## Passer en revue ces ressources avant de commencer

Veillez à consulter ces ressources avant de commencer :

  - Pour plus d’informations sur la configuration matérielle et logicielle requise, [consultez les instructions de planification](plan-office-web-apps-server.md).

  - Par défaut, Office Web Apps Server vous permet d’afficher des fichiers Office, mais pas de les modifier. Pour modifier des fichiers, vous avez besoin d’une licence d’édition. Vous trouverez plus d’informations sur cette licence dans les articles [Planification d'Office Web Apps (utilisé avec SharePoint 2013)](plan-office-web-apps-used-with-sharepoint-2013.md) et [Configurer la gestion des licences dans SharePoint Server 2013](https://technet.microsoft.com/fr-fr/library/jj219627\(v=office.15\)).

> [!NOTE]
> Vous pouvez exécuter des tâches partout dans suites Office 2013 au moyen d’une souris, de raccourcis clavier ou d’entrées tactiles. Pour plus d’informations sur l’utilisation des raccourcis clavier et des entrées tactiles avec les produits et services Office, consultez la rubrique relative aux <a href="https://go.microsoft.com/fwlink/p/?linkid=249150">raccourcis clavier</a> et le <a href="https://go.microsoft.com/fwlink/p/?linkid=253163">Guide des fonctions tactiles dans Office</a>.


## Préparer des serveurs pour l’exécution d’Office Web Apps Server

Effectuez les procédures suivantes sur tous les serveurs qui exécuteront Office Web Apps Server.

**Figure : Étapes de la préparation des serveurs pour Office Web Apps Server**

![Les trois étapes principales pour la préparation des serveurs pour Office Web Apps Server.](images/JJ219455.af2a4690-4f8b-42c3-aab5-f7066bc0a936(Office.15).gif "Les trois étapes principales pour la préparation des serveurs pour Office Web Apps Server.") 

## Étape 1 : installer les logiciels prérequis pour Office Web Apps Server

La configuration requise pour Windows Server 2008 R2, Windows Server 2012 et Windows Server 2012 R2 est légèrement différente ; choisissez la procédure appropriée parmi celles indiquées ci-dessous afin d’installer les logiciels adaptés à votre système d’exploitation.

**Sur Windows Server 2008 R2**

1.  Installez les logiciels suivants :
    
      - [Windows Server 2008 R2 Service Pack 1](http://go.microsoft.com/fwlink/p/?linkid=252370)
    
      - [.NET Framework 4.5](https://go.microsoft.com/fwlink/p/?linkid=256560)
    
      - [Windows PowerShell 3.0](https://go.microsoft.com/fwlink/p/?linkid=244693)
    
      - [Mise à jour de la plate-forme pour Windows 7 SP1 et Windows Server 2008 R2 SP1 (KB2670838)](https://go.microsoft.com/fwlink/p/?linkid=293629)

2.  Ouvrez l’invite Windows PowerShell en tant qu’administrateur et exécutez ces commandes pour installer les rôles et les services requis.
    
    ```PowerShell
        Import-Module ServerManager
    ```
    
    Ensuite, exécutez la commande suivante :
    
    ```PowerShell
        Add-WindowsFeature Web-Server,Web-WebServer,Web-Common-Http,Web-Static-Content,Web-App-Dev,Web-Asp-Net,Web-Net-Ext,Web-ISAPI-Ext,Web-ISAPI-Filter,Web-Includes,Web-Security,Web-Windows-Auth,Web-Filtering,Web-Stat-Compression,Web-Dyn-Compression,Web-Mgmt-Console,Ink-Handwriting,IH-Ink-Support,NET-Framework,NET-Framework-Core,NET-HTTP-Activation,NET-Non-HTTP-Activ,NET-Win-CFAC
    ```
    
    Si vous y êtes invité, redémarrez le serveur.

**Sur Windows Server 2012**

1.  Ouvrez l’invite Windows PowerShell en tant qu’administrateur et exécutez cette commande pour installer les rôles et les services requis.
    
    ```PowerShell
        Add-WindowsFeature Web-Server,Web-Mgmt-Tools,Web-Mgmt-Console,Web-WebServer,Web-Common-Http,Web-Default-Doc,Web-Static-Content,Web-Performance,Web-Stat-Compression,Web-Dyn-Compression,Web-Security,Web-Filtering,Web-Windows-Auth,Web-App-Dev,Web-Net-Ext45,Web-Asp-Net45,Web-ISAPI-Ext,Web-ISAPI-Filter,Web-Includes,InkandHandwritingServices,NET-Framework-Features,NET-Framework-Core,NET-HTTP-Activation,NET-Non-HTTP-Activ,NET-WCF-HTTP-Activation45
    ```
    
    Si vous y êtes invité, redémarrez le serveur.

**Sur Windows Server 2012 R2**

1.  Installez les logiciels suivants :
    
      - [.NET Framework 4.5.2](https://go.microsoft.com/fwlink/p/?linkid=510096)

2.  Ouvrez l’invite Windows PowerShell en tant qu’administrateur et exécutez cette commande pour installer les rôles et les services requis.
    
    ```PowerShell
        Add-WindowsFeature Web-Server,Web-Mgmt-Tools,Web-Mgmt-Console,Web-WebServer,Web-Common-Http,Web-Default-Doc,Web-Static-Content,Web-Performance,Web-Stat-Compression,Web-Dyn-Compression,Web-Security,Web-Filtering,Web-Windows-Auth,Web-App-Dev,Web-Net-Ext45,Web-Asp-Net45,Web-ISAPI-Ext,Web-ISAPI-Filter,Web-Includes,InkandHandwritingServices,NET-Framework-Features,NET-Framework-Core,NET-HTTP-Activation,NET-Non-HTTP-Activ,NET-WCF-HTTP-Activation45
    ```
    
    Si vous y êtes invité, redémarrez le serveur.

## Étape 2 : installer Office Web Apps Server et les mises à jour associées

Effectuez les étapes suivantes sur tous les serveurs qui exécuteront Office Web Apps Server.

1.  Téléchargez Office Web Apps Server à partir du [Centre de gestion des licences en volume](https://go.microsoft.com/fwlink/p/?linkid=256561). Pour télécharger Office Web Apps Server, vous devez disposer d’une licence dans le cadre d’un contrat de licence en volume pour Office Professionnel Plus 2013, Office Standard 2013 ou Office pour Mac 2011. Le téléchargement est disponible sous ces produits Office sur le portail du Centre de gestion des licences en volume.

2.  Effectuez l’une des opérations suivantes :
    
      - Pour Windows Server 2012 ou Windows Server 2012 R2, ouvrez directement le fichier .img et exécutez le fichier **Setup.exe**.
    
      - Pour Windows Server 2008 R2 SP1, utilisez un programme capable de monter ou d’extraire des fichiers .img, puis exécutez **Setup.exe**.

3.  Dans la page **Lire les termes du contrat de licence logiciel Microsoft**, sélectionnez **J’accepte les termes de ce contrat**, puis cliquez sur **Continuer**.

4.  Dans la page **Choisir un emplacement de fichier**, sélectionnez le dossier dans lequel vous souhaitez installer les fichiers Office Web Apps Server (par exemple, C:\\Program Files\\Microsoft Office Web Apps), puis sélectionnez **Installer maintenant**. Si le dossier que vous avez indiqué n’existe pas, le programme d’installation le crée pour vous.
    
    Nous vous conseillons d’installer Office Web Apps Server sur le lecteur système.

5.  Une fois que le programme d’installation a terminé l’installation d’Office Web Apps Server, choisissez **Fermer**.

6.  Téléchargez et installez [Office Web Apps Server SP1](https://go.microsoft.com/fwlink/p/?linkid=510097) (Recommandé pour Windows Server 2012 et Windows Server 2008 R2 SP1. Requis pour Windows Server 2012 R2.)
    
    > [!NOTE]
	> Si vous appliquez Office Web Apps Server SP1 plus tard, suivez les instructions de l’article <a href="apply-software-updates-to-office-web-apps-server.md">Application de mises à jour logicielles pour Office Web Apps Server</a>.


7.  Recherchez les mises à jour Office Web Apps Server les plus récentes parmi la liste du [centre des mises à jour TechNet pour Office, les serveurs Office et les produits associés](https://go.microsoft.com/fwlink/p/?linkid=280271).
    
    > [!NOTE]
	> Si vous n’avez pas installé Office Web Apps Server SP1, appliquez les consignes décrites dans <a href="https://go.microsoft.com/fwlink/p/?linkid=296579">KB2810007</a>.


## Étape 3 : installer les modules linguistiques pour Office Web Apps Server

Les modules linguistiques Office Web Apps Server 2013 permettent aux utilisateurs de consulter des fichiers web Office dans plusieurs langues, qui’ils soient ouverts à partir de bibliothèques de documents SharePoint 2013, d’Outlook Web Access (sous forme d’aperçus des pièces jointes) et de Lync 2013 (sous forme de diffusions PowerPoint). Apprenez-en plus sur le fonctionnement des modules linguistiques dans [Planning language packs for Office Web Apps Server](plan-office-web-apps-server.md).

Pour installer les modules linguistiques, procédez comme suit.


1.  Téléchargez les modules linguistiques Office Web Apps Server à partir du [Centre de téléchargement Microsoft](https://go.microsoft.com/fwlink/p/?linkid=263945).

2.  Exécutez **WebAppsServerLP\_en-us\_x64.exe**.

3.  Dans l’Assistant Module linguistique Office Web Apps Server 2013, dans la page **Lire les termes du contrat de licence logiciel Microsoft**, sélectionnez **J’accepte les termes de ce contrat**, puis cliquez sur **Continuer**.

4.  Une fois que le programme d’installation a terminé l’installation d’Office Web Apps Server, choisissez **Fermer**.

> [!IMPORTANT]
> <ul>
> <li><p>Pour installer les modules linguistiques après avoir créé la batterie de serveurs Office Web Apps Server, vous devez supprimer un serveur de la batterie, installer le module linguistique dessus, puis rajouter le serveur dans la batterie.</p></li>
> <li><p>Pour que le module linguistique fonctionne correctement, vous devrez l’installer sur tous les serveurs de la batterie de serveurs.</p></li>
> </ul>

## Déployer la batterie de serveurs Office Web Apps Server

Suivez la procédure de l’une des trois sections suivantes, en fonction du type de batterie de serveurs Office Web Apps Server que vous voulez créer.

> [!TIP]
> Si Windows PowerShell ne reconnaît pas l’applet de commande <strong>New-OfficeWebAppsFarm</strong> lorsque vous l’exécutez, vous devrez importer le module <strong>OfficeWebApps</strong>. Utilisez la commande suivante :<br />
<code>Import-Module -Name OfficeWebApps</code>


## Déployer une batterie Office Web Apps Server à serveur unique qui utilise le protocole HTTP

Si vous déployez Office Web Apps Server uniquement à des fins de test ou d’utilisation interne, et que vous n’avez pas besoin de fournir la fonctionnalité de Office Web Apps Server à Lync Server 2013, cette procédure est faite pour vous. Ici, vous installerez une batterie Office Web Apps Server à serveur unique qui utilise le protocole HTTP. Vous n’aurez pas besoin de certificat ni de programme d’équilibrage de charge, mais vous devrez disposer d’un serveur physique ou une instance d’ordinateur virtuel dédié qui n’exécute aucune autre application serveur.

Vous pouvez utiliser cette batterie Office Web Apps Server pour distribuer la fonctionnalité Office Web Apps à SharePoint 2013.

**Figure : Étapes du déploiement d’Office Web Apps Server**

![Les trois étapes principales pour le déploiement d’une batterie Office Web Apps Server à serveur unique.](images/JJ219455.de5b3ed2-d7a7-489e-9de2-f3f068ebe836(Office.15).gif "Les trois étapes principales pour le déploiement d’une batterie Office Web Apps Server à serveur unique.")

## Étape 1 : créer la batterie Office Web Apps Server

Utilisez la commande **New-OfficeWebAppsFarm** pour créer une batterie de serveurs Office Web Apps Server qui comporte un serveur unique, comme indiqué dans l’exemple ci-dessous.

```PowerShell
    New-OfficeWebAppsFarm -InternalURL "http://servername" -AllowHttp -EditingEnabled
```

**Paramètres**

  - **–InternalURL** est le nom du serveur qui exécute Office Web Apps Server (par exemple, **http://nom\_serveur**).

  - **–AllowHttp** configure la batterie de serveurs pour utiliser le protocole HTTP.

  - **–EditingEnabled** active la modification dans Office Web Apps en cas d’utilisation avec SharePoint 2013. Ce paramètre n’est pas utilisé par Lync Server 2013 car cet hôte ne prend pas en charge la modification.

Des paramètres supplémentaires pour configurer les services de traduction, les serveurs proxy, la prise en charge des images Clipart et les visionneuses en ligne sont décrits dans [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps).

En cas d'affichage des messages « Exceptions de service web (500) » ou « Erreur interne du serveur (500.21) »

## Étape 2 : vérifier que la batterie Office Web Apps Server a été correctement créée

Une fois la batterie créée, des détails la concernant s’affichent dans l’invite Windows PowerShell. Pour vérifier qu’Office Web Apps Server est installé et configuré correctement, utilisez un navigateur web pour accéder à l’URL de découverte Office Web Apps Server comme le montre l’exemple suivant. L’URL de découverte correspond au paramètre *InternalUrl* que vous avez indiqué lors de la configuration de votre batterie Office Web Apps Server, suivi de **/hosting/discovery**, par exemple :

    http://servername/hosting/discovery

Si Office Web Apps Server fonctionne comme prévu, vous devriez voir apparaître un fichier XML de découverte WOPI dans votre navigateur web. Les premières lignes de ce fichier doivent se présenter comme dans l’exemple suivant.

```xml
    <?xml version="1.0" encoding="utf-8" ?> 
    - <wopi-discovery>
    - <net-zone name="internal-http">
    - <app name="Excel" favIconUrl="http://servername/x/_layouts/images/FavIcon_Excel.ico" checkLicense="true">
    <action name="view" ext="ods" default="true" urlsrc="http://servername/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" /> 
    <action name="view" ext="xls" default="true" urlsrc="http://servername/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" /> 
    <action name="view" ext="xlsb" default="true" urlsrc="http://servername/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" /> 
    <action name="view" ext="xlsm" default="true" urlsrc="http://servername/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" /> 
```

## Étape 3 : configurer l’hôte

La batterie de serveurs est désormais prête à distribuer la fonctionnalité Office Web Apps aux hôtes via HTTP. Pour plus d’informations sur la configuration des hôtes, consultez la rubrique [Configurer Office Web Apps pour SharePoint 2013](configure-office-web-apps-for-sharepoint-2013.md).

## Déploiement d’une batterie Office Web Apps Server à serveur unique qui utilise le protocole HTTPS
<a name="singlehttps"> </a>

Pour la plupart des environnements de production, nous recommandons vivement l’utilisation de HTTPS pour ses fonctionnalités de sécurité. HTTPS est également nécessaire si vous voulez fournir la fonctionnalité Office Web Apps Server à Lync Server 2013, ce qui permet aux utilisateurs d’afficher des diffusions PowerPoint dans un navigateur. Voici comment installer une batterie Office Web Apps Server à serveur unique qui utilise le protocole HTTPS. Vous devez installer un certificat sur le serveur, comme indiqué dans [Sécurisation des communications Office Web Apps Server à l'aide du protocole HTTPS](plan-office-web-apps-server.md).

Cette batterie de serveurs Office Web Apps Server fournira la fonctionnalité Office Web Apps à SharePoint 2013 et Lync Server 2013.

**Figure : Étapes du déploiement d’Office Web Apps Server**

![Les trois étapes principales pour le déploiement d’une batterie Office Web Apps Server à serveur unique.](images/JJ219455.de5b3ed2-d7a7-489e-9de2-f3f068ebe836(Office.15).gif "Les trois étapes principales pour le déploiement d’une batterie Office Web Apps Server à serveur unique.")

## Étape 1 : créer la batterie Office Web Apps Server

Utilisez la commande **New-OfficeWebAppsFarm** pour créer une batterie de serveurs Office Web Apps Server qui comporte un serveur unique, comme indiqué dans l’exemple ci-dessous.

```PowerShell
    New-OfficeWebAppsFarm -InternalUrl "https://server.contoso.com" -ExternalUrl "https://wacweb01.contoso.com" -CertificateName "OfficeWebApps Certificate" -EditingEnabled
```

**Paramètres**

  - **–InternalURL** est le nom de domaine complet (FQDN) du serveur qui exécute Office Web Apps Server, tel que **http://nom\_serveur.contoso.com**.

  - **–ExternalURL** est le nom de domaine complet qui est accessible sur Internet.

  - **–CertificateName** est le nom convivial du certificat.

  - **–EditingEnabled** est facultatif et active la modification dans Office Web Apps en cas d’utilisation avec SharePoint 2013. Ce paramètre n’est pas utilisé par Lync Server 2013 car cet hôte ne prend pas en charge la modification.

Des paramètres supplémentaires pour configurer les services de traduction, les serveurs proxy, la prise en charge des images Clipart et les visionneuses en ligne sont décrits dans [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps).

En cas d'affichage des messages « Exceptions de service web (500) » ou « Erreur interne du serveur (500.21) »

## Étape 2 : vérifier que la batterie Office Web Apps Server a été correctement créée

Une fois la batterie créée, des détails la concernant s’affichent dans l’invite Windows PowerShell. Pour vérifier qu’Office Web Apps Server est installé et configuré correctement, utilisez un navigateur web pour accéder à l’URL de découverte Office Web Apps Server comme le montre l’exemple suivant. L’URL de découverte correspond au paramètre *InternalUrl* que vous avez indiqué lors de la configuration de votre batterie Office Web Apps Server, suivi de **/hosting/discovery**, par exemple :

```
    https://server.contoso.com/hosting/discovery
```

Si Office Web Apps Server fonctionne comme prévu, vous devriez voir apparaître un fichier XML de découverte WOPI dans votre navigateur web. Les premières lignes de ce fichier doivent se présenter comme dans l’exemple suivant.

```XML 
<?xml version="1.0" encoding="UTF-8"?>
<wopi-discovery><net-zone 
name="internal-https"><app name="Excel" checkLicense="true" 
favIconUrl="https://wac.contoso.com/x/_layouts/images/FavIcon_Excel.ico"><action 
name="view" 
urlsrc="https://wac.contoso.com/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" 
default="true" ext="ods"/><action name="view" 
urlsrc="https://wac.contoso.com/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" 
default="true" ext="xls"/><action name="view" 
```

> [!NOTE]
> Selon les paramètres de sécurité de votre navigateur web, il est possible qu’un message vous invite à sélectionner <strong>Afficher tout le contenu</strong> avant de pouvoir afficher le contenu du fichier XML de découverte.


## Étape 3 : configurer l’hôte

La batterie de serveurs est maintenant prête à distribuer la fonctionnalité Office Web Apps aux hôtes via HTTPS. Consultez les articles suivants pour obtenir de plus amples informations sur la manière de configurer des hôtes.

  - [Configurer Office Web Apps pour SharePoint 2013](configure-office-web-apps-for-sharepoint-2013.md)

  - [Déploiement d’Office Web Apps Server et de Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=256902)

## Déploiement d’une batterie Office Web Apps Server multiserveur à charge équilibrée qui utilise le protocole HTTPS
<a name="multihttps"> </a>

Si vous prévoyez un trafic important vers votre batterie de serveurs Office Web Apps Server, et si vous voulez que celle-ci soit disponible via Internet et sur votre réseau interne, ce type de topologie est idéal. Cette section vous montre comment installer une batterie Office Web Apps Server multiserveur qui utilise un programme d’équilibrage de charge et le protocole HTTPS. Si vous êtes intéressé, [apprenez-en plus sur la topologie](plan-office-web-apps-server.md).

Avant de commencer, assurez-vous que le programme d’équilibrage de charge est configuré comme indiqué dans [Configuration requise du programme d'équilibrage de charge pour Office Web Apps Server](plan-office-web-apps-server.md). Vous devez également installer un certificat sur le programme d’équilibrage de charge, comme indiqué dans [Sécurisation des communications Office Web Apps Server à l'aide du protocole HTTPS](plan-office-web-apps-server.md). Cette batterie de serveurs Office Web Apps Server fournira la fonctionnalité Office Web Apps à SharePoint 2013 et Lync Server 2013.

**Figure : Étapes du déploiement d’Office Web Apps Server**

![Les quatre étapes principales pour le déploiement d’une batterie Office Web Apps Server multiserveur.](images/JJ219455.4c4b31cb-961b-4efd-b755-a18bdcb5c191(Office.15).gif "Les quatre étapes principales pour le déploiement d’une batterie Office Web Apps Server multiserveur.")

## Étape 1 : créer la batterie Office Web Apps Server sur le premier serveur

Utilisez la commande **New-OfficeWebAppsFarm** pour créer une batterie de serveurs Office Web Apps Server sur le premier serveur, comme indiqué dans l’exemple suivant.

```PowerShell
    New-OfficeWebAppsFarm -InternalUrl "https://server.contoso.com" -ExternalUrl "https://wacweb01.contoso.com" -SSLOffloaded -EditingEnabled
```

**Paramètres**

  - **–InternalURL** est le nom de domaine complet (FQDN) du serveur qui exécute Office Web Apps Server, tel que **http://nom\_serveur.contoso.com**.

  - **–ExternalURL**est le nom de domaine complet qui est accessible sur Internet.

  - **-SSLOffloaded** active le déchargement de l’arrêt SSL vers le programme d’équilibrage de charge.

  - **–EditingEnabled** est facultatif et active la modification dans Office Web Apps en cas d’utilisation avec SharePoint 2013. Ce paramètre n’est pas utilisé par Lync Server 2013 car cet hôte ne prend pas en charge la modification.

D’autres paramètres pour configurer les services de traduction, les serveurs proxy, la prise en charge des images Clipart et les visionneuses en ligne sont décrits dans [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps).

En cas d'affichage des messages « Exceptions de service web (500) » ou « Erreur interne du serveur (500.21) »

## Étape 2 : ajouter d’autres serveurs à la batterie

Une fois que le premier serveur exécute Office Web Apps Server, exécutez la commande **New-OfficeWebAppsMachine** sur chaque serveur que vous voulez ajouter à la batterie de serveurs Office Web Apps Server. Pour le paramètre **–MachineToJoin**, utilisez le nom d’ordinateur d’un serveur qui se trouve déjà dans la batterie de serveurs Office Web Apps Server. Par exemple, si server1.contoso.com est déjà dans la batterie de serveurs, utilisez les éléments suivants :

```PowerShell
    New-OfficeWebAppsMachine -MachineToJoin "server1.contoso.com"
```

Vous souhaitez plus d’informations sur ces paramètres ? Vous en trouverez dans la rubrique [New-OfficeWebAppsMachine](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsmachine?view=officewebapps-ps).

## Étape 3 : vérifier que la batterie Office Web Apps Server a été correctement créée

Une fois la batterie créée, des détails la concernant s’affichent dans l’invite Windows PowerShell. Pour vérifier qu’Office Web Apps Server est installé et configuré correctement, utilisez un navigateur web pour accéder à l’URL de découverte Office Web Apps Server comme le montre l’exemple suivant. L’URL de découverte correspond au paramètre *InternalUrl* que vous avez indiqué lors de la configuration de votre batterie Office Web Apps Server, suivi de **/hosting/discovery**. Par exemple :

    https://server.contoso.com/hosting/discovery

Si Office Web Apps Server fonctionne comme prévu, vous devriez voir apparaître un fichier XML de découverte WOPI dans votre navigateur web. Les premières lignes de ce fichier doivent se présenter comme dans l’exemple suivant.

```XML
    <?xml version="1.0" encoding="UTF-8"?>
    <wopi-discovery><net-zone name="internal-https"><app name="Excel" checkLicense="true" favIconUrl="https://officewebapps.contoso.com/x/_layouts/images/FavIcon_Excel.ico"><action name="view" urlsrc="https://officewebapps.contoso.com/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" default="true" ext="ods"/><action name="view" urlsrc="https://officewebapps.contoso.com/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" default="true" ext="xls"/><action name="view" urlsrc="https://officewebapps.contoso.com/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" default="true" ext="xlsb"/> 
```

> [!NOTE]
> Selon les paramètres de sécurité de votre navigateur web, il est possible qu’un message vous invite à sélectionner <strong>Afficher tout le contenu</strong> avant de pouvoir afficher le contenu du fichier XML de découverte.


## Étape 4 : configurer l’hôte

La batterie de serveurs est maintenant prête à distribuer la fonctionnalité Office Web Apps aux hôtes via HTTPS. Consultez les articles suivants pour obtenir de plus amples informations sur la manière de configurer des hôtes.

  - [Configurer Office Web Apps pour SharePoint 2013](configure-office-web-apps-for-sharepoint-2013.md)

  - [Déploiement d’Office Web Apps Server et de Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=256902)

## En cas d’affichage des messages « Exceptions de service web (500) » ou « Erreur interne du serveur (500.21) »

Si des fonctionnalités de .NET Framework 3.5 ont été installées puis supprimées, il est possible que vous rencontriez des messages de type « Exceptions de service web (500) » ou « Erreur interne du serveur (500.21) » lorsque vous exécutez des cmdlets OfficeWebApps. Pour résoudre ces problèmes, exécutez les exemples de commandes suivants à partir d’une invite de commandes avec élévation de privilèges afin de supprimer les paramètres susceptibles de gêner le fonctionnement normal d’Office Web Apps Server :

**Pour Windows Server 2008 R2**

```PowerShell
    %systemroot%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe -iru

    iisreset /restart /noforce
```
**Pour Windows Server 2012 ou Windows Server 2012 R2**

```PowerShell
    dism /online /enable-feature /featurename:IIS-ASPNET45
```

## Voir aussi


[New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps)  
[New-OfficeWebAppsMachine](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsmachine?view=officewebapps-ps)  


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Planification d'Office Web Apps Server](plan-office-web-apps-server.md)  
[Configurer Office Web Apps pour SharePoint 2013](configure-office-web-apps-for-sharepoint-2013.md)  


[Déploiement d’Office Web Apps Server et de Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=256902)  
  

[](configure-office-web-apps-for-sharepoint-2013.md)

