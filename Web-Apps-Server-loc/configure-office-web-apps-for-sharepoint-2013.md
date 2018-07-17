---
title: Configurer Office Web Apps pour SharePoint 2013
TOCTitle: Configurer Office Web Apps pour SharePoint 2013
ms:assetid: a5276781-133b-413c-beca-b851e17c2081
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Ff431687(v=office.15)
ms:contentKeyID: 49645223
ms.date: 12/24/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Configurer Office Web Apps pour SharePoint 2013

 

_<strong>Sapplique à :</strong>Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_<strong>Dernière rubrique modifiée :</strong>2016-12-16_


**Résumé** : découvrez comment configurer SharePoint 2013 pour utiliser Office Web Apps.

**Public concerné** : professionnels de l’informatique

Cet article reprend là où [Déployer Office Web Apps Server](deploy-office-web-apps-server.md) s’est arrêté. Cet article-là permettait de configurer le serveur qui exécute Office Web Apps Server. Avec celui-ci, vous allez configurer SharePoint 2013 afin d’utiliser Office Web Apps Server. Vous devrez d’abord exécuter quelques cmdlets Windows PowerShell à partir de SharePoint 2013. Les utilisateurs pourront ensuite ouvrir des fichiers Office à partir des bibliothèques de documents SharePoint 2013 dans un navigateur.

Si vous ne connaissez pas les fonctionnalités d’Office Web Apps Server, [consultez la rubrique Vue d’ensemble](office-web-apps-server-overview.md).

Contenu de cet article :

  - Avant de configurer SharePoint 2013 pour l’utilisation d’Office Web Apps Server

  - Configurer SharePoint 2013 pour l’utilisation d’Office Web Apps Server

  - Résolution des erreurs dans Office Web Apps avec l'utilisation conjointe de SharePoint 2013

  - Déconnexion de SharePoint 2013 d'Office Web Apps Server

## Avant de configurer SharePoint 2013 pour l’utilisation d’Office Web Apps Server

Voici quelques points à vérifier avant de commencer :

  - Installez SharePoint 2013. Voir [Installer SharePoint 2013](https://technet.microsoft.com/fr-fr/library/cc303424\(v=office.15\)) à titre indicatif.

  - Assurez-vous que toutes les applications web SharePoint 2013 utilisent l’authentification basée sur les revendications. Le rendu et la modification Office Web Apps ne fonctionneront pas dans des applications web SharePoint 2013 qui utilisent l’authentification en mode classique. Découvrez-en plus dans la section [Spécifications de l'authentification SharePoint pour Office Web Apps](plan-office-web-apps-used-with-sharepoint-2013.md).

  - Pour permettre aux utilisateurs de modifier (et pas simplement lire) des documents Office dans un navigateur web, vous avez besoin d’une licence d’accès en modification. En outre, vous devez activer la modification dans la batterie Office Web Apps Server. Vous en apprendrez plus sur les conditions de licence requises dans [Licensing Office Web Apps for editing Office files](plan-office-web-apps-used-with-sharepoint-2013.md).

  - Si vous vous connectez à SharePoint 2013 avec le compte système, vous ne pourrez pas tester la connexion entre SharePoint 2013 et Office Web Apps Server. Pour tester la connexion, connectez-vous avec un autre compte.

  - Des conditions de mémoire insuffisante peuvent entraîner l’échec des aperçus des documents Office dans Office Web Apps. Consultez l’article, [Configuration matérielle requise (serveurs web, serveurs d'applications et installations sur un seul serveur)](https://technet.microsoft.com/fr-fr/4d88c402-24f2-449b-86a6-6e7afcfec0cd\(office.15\)#hwforwebserver) pour SharePoint 2013, qui est la même configuration que celle requise pour Office Web Apps Server.

## Configurer SharePoint 2013 pour l’utilisation d’Office Web Apps Server

Choisissez l’une des sections suivantes selon que vous voulez utiliser le protocole HTTP ou HTTPS. HTTP est généralement recommandé uniquement pour les environnements de test. Dans les environnements de production, le protocole HTTPS, plus sécurisé, est le meilleur choix.

## Dans un environnement de test qui utilise HTTP

Pour cette configuration, assurez-vous que vous avez configuré Office Web Apps Server selon les étapes indiquées dans [Déployer une batterie Office Web Apps Server à serveur unique dans un environnement de test](deploy-office-web-apps-server.md). Assurez-vous que vous avez configuré la batterie de serveurs Office Web Apps Server afin d’utiliser le protocole HTTP et une URL interne. La [Vidéo : Configurer Office Web Apps pour SharePoint 2013](video-configure-office-web-apps-for-sharepoint-2013.md) vous montre comment configurer Office Web Apps Server et SharePoint 2013 pour utiliser Office Web Apps Server dans un environnement de test.

## Étape 1 : ouvrir SharePoint 2013 Management Shell avec des privilèges élevés

Choisissez la procédure qui correspond à votre système d’exploitation serveur.

**Dans Windows Server 2008 R2**

1.  Cliquez sur **Démarrer** \> **Tous les programmes** \> **Produits Microsoft SharePoint 2013**.

2.  Cliquez avec le bouton droit sur **SharePoint 2013 Management Shell**, puis cliquez sur **Exécuter en tant qu’administrateur**.

**Dans Windows Server 2012**

1.  Appuyez sur la touche Windows + Q, ou effectuez un balayage en partant du bord de façon à afficher les icônes, puis cliquez sur **Rechercher** pour afficher toutes les applications installées sur l’ordinateur.

2.  Cliquez avec le bouton droit sur **SharePoint 2013 Management Shell** pour afficher la barre de l’application.

3.  Dans la barre de l’application, cliquez sur **Exécuter en tant qu’administrateur**.

## Étape 2 : créer la liaison entre SharePoint 2013 et Office Web Apps Server

Exécutez la commande suivante où \<WacServerName\> désigne le nom de domaine complet (FQDN) de l’URL que vous avez définie pour l’URL interne. Il s’agit du point d’entrée du trafic Office Web Apps Server. Pour cet environnement de test, vous devez spécifier le paramètre –AllowHTTP pour autoriser SharePoint 2013 à recevoir des informations de découverte de la batterie Office Web Apps Server à l’aide du protocole HTTP. Si vous ne spécifiez pas le paramètre –AllowHTTP, SharePoint 2013 essaiera d’utiliser le protocole HTTPS avec la batterie Office Web Apps Server et cette commande ne fonctionnera pas.

```PowerShell
    New-SPWOPIBinding -ServerName <WacServerName> -AllowHTTP
```

Après avoir exécuté cette commande, vous devez voir une liste de liaisons s’afficher à l’invite de commandes Windows PowerShell.

Vous avez besoin d’aide ? Consultez [New-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPIBinding?view=sharepoint-ps).

## Étape 3 : afficher les zones WOPI pour les liaisons SharePoint

Office Web Apps Server utilise des zones pour déterminer l’URL (interne ou externe) et le protocole (HTTP ou HTTPS) à utiliser au moment de communiquer avec l’hôte, soit SharePoint 2013 dans le cas présent. Par défaut, SharePoint Server 2013 utilise la zone **internal-https**. Vérifiez qu’il s’agit de la zone actuelle en exécutant la commande suivante :

```PowerShell
    Get-SPWOPIZone
```

La zone WOPI affichée par cette commande doit être **internal-http**. Si elle s’affiche correctement, passez à l’étape 5. Dans le cas contraire, reportez-vous à l’étape suivante.

Vous avez besoin d’aide ? Voir [Get-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIZone?view=sharepoint-ps).

## Étape 4 : modifier la zone WOPI en internal-http

Si le résultat de l’étape 3 était **internal-https**, exécutez la commande suivante pour redéfinir la zone en **internal-http**. Ce changement est obligatoire car la zone SharePoint 2013 doit correspondre à la zone de la batterie Office Web Apps Server.

```PowerShell
    Set-SPWOPIZone -zone "internal-http"
```

Vérifiez que la nouvelle zone est **internal-http** en exécutant **Get-SPWOPIZone** à nouveau.

Vous avez besoin d’aide ? Voir [Set-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIZone?view=sharepoint-ps) et [Get-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIZone?view=sharepoint-ps).

## Étape 5 : modifier le paramètre AllowOAuthOverHttp dans SharePoint 2013 en lui donnant la valeur True

Pour utiliser Office Web Apps avec SharePoint 2013 sur HTTP dans un environnement de test, vous devez définir le paramètre AllowOAuthOverHttp sur **True** sans quoi Office Web Apps ne fonctionnera pas. Vous pouvez vérifier l’état actuel en appliquant l’exemple suivant.

```PowerShell
    (Get-SPSecurityTokenServiceConfig).AllowOAuthOverHttp
```

Si cette commande renvoie la valeur **False**, exécutez les commandes suivantes pour la définir sur **True**.

```PowerShell
    $config = (Get-SPSecurityTokenServiceConfig)
```

```PowerShell
    $config.AllowOAuthOverHttp = $true
```

```PowerShell
    $config.Update()
```

Exécutez de nouveau la commande suivante pour vérifier que le paramètre AllowOAuthOverHttp est à présent défini sur **True**.

```PowerShell
    (Get-SPSecurityTokenServiceConfig).AllowOAuthOverHttp
```

Vous avez besoin d’aide ? Consultez [Get-SPSecurityTokenServiceConfig](https://technet.microsoft.com/fr-fr/library/ff607642\(v=office.15\)).

## Étape 6 : vérifier qu’Office Web Apps fonctionne

Dans SharePoint 2013, assurez-vous que vous n’êtes pas connecté en tant que compte système car vous ne pourrez pas modifier ou afficher les documents à l’aide d’Office Web Apps. Accédez à une bibliothèque de documents SharePoint 2013 qui contient des documents Office et affichez un fichier Word, PowerPoint, Excel ou OneNote. Le document doit s’ouvrir dans un navigateur qui affiche le fichier au moyen d’Office Web Apps.

Si cette étape échoue, consultez Résolution des erreurs dans Office Web Apps.

## Dans un environnement de production qui utilise le protocole HTTPS

Avant d’entamer les procédures suivantes, assurez-vous d’avoir configuré Office Web Apps Server en effectuant les étapes décrites dans la section [Déploiement d'une batterie Office Web Apps Server à serveur unique qui utilise le protocole HTTPS](deploy-office-web-apps-server.md#singlehttps) ou [Déployer une batterie Office Web Apps Server multiserveur à charge équilibrée qui utilise le protocole HTTPS](deploy-office-web-apps-server.md#multihttps).

## Étape 1 : ouvrir SharePoint 2013 Management Shell

Choisissez la procédure qui correspond à votre système d’exploitation serveur.

**Dans Windows Server 2008 R2**

1.  Sélectionnez **Démarrer** \> **Tous les programmes** \> **Produits Microsoft SharePoint 2013**.

2.  Cliquez avec le bouton droit sur **SharePoint 2013 Management Shell** pour afficher le menu contextuel, puis cliquez sur **Exécuter en tant qu’administrateur**.

**Dans Windows Server 2012**

1.  Appuyez sur la touche Windows + Q, ou effectuez un balayage en partant du bord de façon à afficher les icônes, puis cliquez sur **Rechercher** pour afficher toutes les applications installées sur l’ordinateur.

2.  Cliquez avec le bouton droit sur **SharePoint 2013 Management Shell** pour afficher la barre de l’application.

3.  Dans la barre de l’application, cliquez sur **Exécuter en tant qu’administrateur**.

## Étape 2 : créer la liaison entre SharePoint 2013 et Office Web Apps Server

Exécutez la commande suivante où \<WacServerName\> désigne le nom de domaine complet (FQDN) de l’URL que vous avez définie pour l’URL interne. Il s’agit du point d’entrée du trafic Office Web Apps Server.

```PowerShell
    New-SPWOPIBinding -ServerName <WacServerName> 
```

Vous avez besoin d’aide ? Consultez [New-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPIBinding?view=sharepoint-ps).

## Étape 3 : afficher la zone WOPI de SharePoint 2013

Office Web Apps Server utilise des zones pour déterminer l’URL (interne ou externe) et le protocole (HTTP ou HTTPS) à utiliser au moment de communiquer avec l’hôte, soitSharePoint 2013 dans le cas présent. Par défaut, SharePoint Server 2013 utilise la zone **internal-https**. Vérifiez qu’il s’agit de la zone actuelle en exécutant la commande suivante.

```PowerShell
    Get-SPWOPIZone
```

Prenez note de la zone WOPI qui s’affiche.

Vous avez besoin d’aide ? Consultez [Get-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIZone?view=sharepoint-ps).

## Étape 4 : modifier la zone WOPI si nécessaire

En fonction de votre environnement, vous devrez peut-être modifier la zone WOPI. Si vous avez une batterie de serveurs SharePoint qui est à la fois interne et externe, spécifiez externe. Si votre batterie de serveurs SharePoint est exclusivement interne, précisez interne.

Si les résultats de l’étape 3 affichent **internal-https** et que la batterie de serveurs SharePoint est uniquement interne, vous pouvez passer outre cette étape. Si vous avez une batterie de serveurs SharePoint interne et externe à la fois, vous devez exécuter la commande suivante pour modifier la zone et la redéfinir en **external-https**.

```PowerShell
    Set-SPWOPIZone -zone "external-https"
```

Vous avez besoin d’aide ? Consultez [Set-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIZone?view=sharepoint-ps).

## Étape 5 : vérifier qu’Office Web Apps fonctionne

Dans SharePoint 2013, assurez-vous que vous n’êtes pas connecté en tant que compte système car vous ne pourrez pas modifier ou afficher les documents à l’aide d’Office Web Apps. Accédez à une bibliothèque de documents SharePoint 2013 qui contient des documents Office et affichez un fichier Word, PowerPoint, Excel ou OneNote. Le document doit s’ouvrir dans un navigateur qui affiche le fichier au moyen d’Office Web Apps.

Si cette étape échoue, consultez la rubrique Résolution des erreurs dans Office Web Apps.

## Résolution des erreurs dans Office Web Apps avec l’utilisation conjointe de SharePoint 2013

Si Office Web Apps ne fonctionne pas correctement lorsque vous l’utilisez conjointement avec SharePoint 2013, recherchez le symptôme ci-dessous et développez le titre pour rechercher la procédure de résolution.

## Problème : lorsque vous sélectionnez le lien « nouveau document » dans une bibliothèque SharePoint, le système vous demande de charger un document plutôt que de créer un document Office. Le choix (simple clic) d’un document Office ouvre le fichier dans l’application cliente. Les aperçus des documents Office ne sont pas affichés.

Voici quelques options de résolution à tenter :

**Vérifiez que l’application web SharePoint a recours à l’authentification basée sur les revendications pour créer le nouveau document**

Seules des applications web utilisant l’authentification basée sur les revendications peuvent ouvrir les fichiers dans Office Web Apps. Pour déterminer le fournisseur d’authentification pour une application web, procédez comme suit :

1.  Dans l’Administration centrale de SharePoint 2013, cliquez sur **Gérer les applications web**.

2.  Sélectionnez l’application web à vérifier, puis cliquez sur **Fournisseurs d’authentification** dans le ruban.

Pour fonctionner correctement avec l’application web, le fournisseur d’authentification doit apparaître sous la forme **Authentification basée sur les revendications** pour Office Web Apps. Pour résoudre ce problème, vous devez supprimer l’application web et la recréer au moyen de l’authentification basée sur les revendications, ou modifier la méthode d’authentification de l’application web. Vous trouverez plus d’informations dans [Spécifications de l'authentification SharePoint pour Office Web Apps](plan-office-web-apps-used-with-sharepoint-2013.md).

**Assurez-vous que les zones WOPI correspondent dans SharePoint 2013 et la batterie de serveurs Office Web Apps Server.**

Pour cela, exécutez la commande suivante dans SharePoint Server :

```PowerShell
    Get-SPWopiZone 
```

Le résultat sera l’une des valeurs suivantes :

  - internal-https

  - internal-http

  - external-https

  - external-http

Exécutez ensuite la commande suivante dans SharePoint Server.

```PowerShell
    Get-SPWOPIBinding
```

Dans la sortie, recherchez **WopiZone : *zone***. Si les résultats de Get-SPWopiZone ne correspondent pas à la zone renvoyée par Get-SPWOPIBinding, exécutez la cmdlet **Set-SPWOPIZone -Zone** dans SharePoint Server pour modifier la zone WOPI afin qu’elle corresponde au résultat de Get-SPWOPIBinding. Pour obtenir de l’aide sur l’utilisation de ces cmdlets, voir [Get-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIBinding?view=sharepoint-ps), [Set-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIBinding?view=sharepoint-ps) et [Get-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIZone?view=sharepoint-ps).

## Problème : vous recevez une erreur de type « Désolé, ce document ne peut pas être ouvert pour modification » lorsque vous essayez de modifier un document Office dans Office Web Apps.

Dans certains cas, les utilisateurs membres de groupes de sécurité Active Directory (AD) ne peuvent pas modifier les documents dans le navigateur. Pour résoudre ce problème, assurez-vous que l’application de service de profil utilisateur est correctement configurée et entièrement synchronisée avec l’utilisateur et les appartenances au groupe. Pour plus d’informations, consultez l’article de la base de connaissances [SharePoint 2013 - Impossible de modifier les fichiers Office Web Apps 2013 avec des utilisateurs membres de groupes de sécurité](https://support.microsoft.com/kb/2908321).

## Problème : vous recevez une erreur de type « Désolé, un problème est survenu » lorsque vous tentez d’afficher un document Office dans Office Web Apps.

Assurez-vous que vous n’êtes pas connecté en tant que compte système car vous ne pourrez ni modifier ni visualiser un document. Connectez-vous avec un autre compte utilisateur, puis essayez à nouveau d’accéder à Office Web Apps.

## Problème : vous recevez une erreur de type « Désolé, un problème est survenu et il est impossible d’ouvrir ce document » lorsque vous tentez d’afficher un document Office dans Office Web Apps.

Si vous avez configuré Office Web Apps dans un environnement de test qui utilise le protocole HTTP, vérifiez que vous avez défini le paramètre AllowOAuthOverHttp sur **True** comme décrit dans Étape 5 : modifier le paramètre AllowOAuthOverHttp dans SharePoint 2013 en lui donnant la valeur True.

Si vous avez ajouté des domaines à la liste verte en utilisant la cmdlet [New-OfficeWebAppsHost](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappshost?view=officewebapps-ps), vérifiez que vous accédez à Office Web Apps à partir d’un domaine hôte faisant partie de la liste verte. Pour afficher les domaines hôtes dans la liste verte, sur le Office Web Apps Server ouvrez l’invite Windows PowerShell en tant qu’administrateur, puis exécutez la cmdlet [Get-OfficeWebAppsHost](https://docs.microsoft.com/en-us/powershell/module/officewebapps/get-officewebappshost?view=officewebapps-ps). Pour ajouter un domaine à la liste verte, utilisez la cmdlet [New-OfficeWebAppsHost](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappshost?view=officewebapps-ps).

## Problème : vous recevez une erreur de type « Désolé... Word Web App ne peut pas ouvrir ce document, car le service est occupé. Veuillez réessayer plus tard. » lorsque vous essayez d’afficher un document Office dans Office Web Apps.

  - Par hasard, n’auriez-vous pas installé Office Web Apps Server sur un contrôleur de domaine ? Malheureusement, Office Web Apps Server ne peut pas être exécuté sur un contrôleur de domaine. Office Web Apps Server doit être installé sur un serveur distinct appartenant à un domaine. Pour en savoir plus, voir [Exigences en matière de logiciel, de matériel, et de configuration pour Office Web Apps Server](plan-office-web-apps-server.md).

  - Assurez-vous que vous exécutez la version 15.0.4420.1017 de SharePoint 2013 ou une version ultérieure. Sur le serveur SharePoint 2013, procédez comme suit pour vérifier le numéro de version :
    
    1.  Accédez à **Démarrer** \> **Tous les programmes** \> **Produits Microsoft SharePoint 2013** \> **Administration centrale de SharePoint 2013**.
    
    2.  Choisissez **Paramètres système** \> **Gérer les serveurs de cette batterie de serveurs**.
    
    Vérifiez que la **version de la base de données de configuration** est bien **15.0.4420.1017** ou une version ultérieure. Si ce n’est pas le cas, accédez au [Centre de mise à jour pour Office, les serveurs Office et les produits associés](https://go.microsoft.com/fwlink/p/?linkid=160585) pour plus d’informations.

## Problème : vous recevez une erreur de type « Fichier introuvable. L’URL du fichier d’origine n’est pas valide ou le document n’est pas accessible publiquement. Vérifiez que l’URL est correcte, puis contactez le propriétaire du document » lorsque vous essayez d’afficher un document Office dans Office Web Apps en utilisant une URL générée par l’utilisateur.

Essayez-vous d’ouvrir un document dont la taille de fichier est supérieure à 10 Mo à partir d’une URL générée par l’utilisateur ? Vérifiez que votre document ne dépasse pas les 10 Mo.

## Problème : les aperçus des documents Office n’apparaissent pas dans SharePoint 2013. À la place, ils affichent l’erreur « Ce contenu ne peut pas être affiché dans un cadre ».

Des conditions de mémoire insuffisante peuvent provoquer des problèmes avec les aperçus des documents Office. Consultez la rubrique [Configuration matérielle requise (serveurs web, serveurs d'applications et installations sur un seul serveur)](https://technet.microsoft.com/fr-fr/4d88c402-24f2-449b-86a6-6e7afcfec0cd\(office.15\)#hwforwebserver) pour connaître les exigences mémoire requises pour SharePoint 2013. Elles sont identiques à celles appliquées par Office Web Apps Server.

## Problème : vous recevez une erreur de type « Une connexion de données est définie pour toujours utiliser un fichier de connexion et {0:ExcelWebApp} ne prend pas en charge les fichiers de connexion externes. Nous n’avons pas pu actualiser la connexion suivante : Connexion de données. »

Ceci se produit, car Office Web Apps Server ne prend pas en charge le fichier de connexion de données Office (ODC) stockant les informations de connexions de données. Pour résoudre ce problème, procédez comme suit :

1.  Ouvrez le classeur dans une application cliente Excel.

2.  Cliquez sur **Données** \> **Connexions**.

3.  Sélectionnez les connexions de données répertoriées dans le message, puis cliquez sur **Propriétés**.

4.  Cliquez sur l’onglet **Définition**.

5.  Décochez l’option **Toujours utiliser un fichier de connexion pour**.

6.  Téléchargez de nouveau le classeur vers la bibliothèque de documents SharePoint.

Pour permettre aux utilisateurs d’interagir avec les classeurs contenant un modèle de données ou des vues Power View dans une fenêtre de navigateur, configurez Excel Services dans SharePoint Server pour afficher les classeurs. Pour cela, un administrateur SharePoint doit exécuter la cmdlet New-SPWOPISupressionSetting sur le serveur où SharePoint Server est installé. Pour en savoir plus, consultez [New-SPWOPISuppressionSetting](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPISuppressionSetting?view=sharepoint-ps) et [Administrer Excel Services dans SharePoint Server 2013](https://technet.microsoft.com/fr-fr/library/ee681487\(v=office.15\)).

## Déconnexion de SharePoint 2013 d’Office Web Apps Server

Si, pour une raison quelconque, vous cherchez à déconnecter SharePoint 2013 d’Office Web Apps Server, utilisez l’exemple de commande suivant.

```PowerShell
    Remove-SPWOPIBinding -All:$true
```

Vous avez besoin d’aide ? Consultez [Remove-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Remove-SPWOPIBinding?view=sharepoint-ps).

## Voir aussi


[New-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPIBinding?view=sharepoint-ps)  
[Set-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIZone?view=sharepoint-ps)  


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Déployer Office Web Apps Server](deploy-office-web-apps-server.md)  
  

[](deploy-office-web-apps-server.md)

