---
title: Application de mises à jour logicielles pour Office Web Apps Server
TOCTitle: Application de mises à jour logicielles pour Office Web Apps Server
ms:assetid: 5d15dbd9-374e-422a-a870-43270dd0a2db
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ966220(v=office.15)
ms:contentKeyID: 51658290
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Application de mises à jour logicielles pour Office Web Apps Server

 

_<strong>Sapplique à :</strong>Office Web Apps Server_

_<strong>Dernière rubrique modifiée :</strong>2016-12-16_

**Résumé** : explique comment appliquer des mises à jour logicielles dans une batterie de serveurs Office Web Apps Server.

**Public concerné** : professionnels de l'informatique

Suite à la publication d'une nouvelle version d'Office Web Apps Server, Microsoft met à disposition une série de mises à jour logicielles visant à améliorer la sécurité, les performances et la fiabilité du serveur. Cet article décrit comment appliquer des mises à jour logicielles sur des serveurs individuels dans une batterie de serveurs Office Web Apps Server.

<table>
<thead>
<tr class="header">
<th><img src="images/Ff431682.important(Office.15).gif" title="Important" alt="Important" /><strong>Important :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Cet article s’inscrit dans la <a href="content-roadmap-for-office-web-apps-server.md">Feuille de route de contenu pour Office Web Apps</a>. Utilisez cette feuille de route comme point de départ pour accéder à des articles, téléchargements et vidéos qui vous aideront à déployer et gérer Office Web Apps Server.<br />
<strong>Vous souhaitez obtenir de l’aide sur Office Web Apps sur les ordinateurs de bureau ou appareils mobiles ?</strong> Pour trouver les informations qui vous intéressent, recherchez « Office Web Apps » sur <a href="http://go.microsoft.com/fwlink/p/?linkid=324961">Office.com</a>.</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<th><img src="images/JJ966220.warning(Office.15).gif" title="Avertissement" alt="Avertissement" /><strong>Avertissement :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>L'application de mises à jour Office Web Apps Server à l'aide du processus de mise à jour automatique n'est pas prise en charge avec Office Web Apps Server. Cela est dû au fait que les mises à jour Office Web Apps Server doivent être appliquées d'une certaine manière, comme indiqué dans le présent article. Si des mises à jour Office Web Apps Server sont appliquées automatiquement, les utilisateurs risquent de ne pas pouvoir afficher ou modifier de documents dans Office Web Apps. Si cette situation se produit, vous devrez reconstruire votre batterie Office Web Apps Server. Pour ce faire, vous devez supprimer le serveur Office Web Apps Server de la batterie à l'aide de <a href="https://docs.microsoft.com/en-us/powershell/module/officewebapps/remove-officewebappsmachine?view=officewebapps-ps">Remove-OfficeWebAppsMachine</a>, désinstaller Office Web Apps Server dans Ajout/Suppression de programmes, puis réinstaller Office Web Apps Server en suivant la procédure décrite dans la rubrique <a href="deploy-office-web-apps-server.md">Déployer Office Web Apps Server</a>. Après la réinstallation, appliquez la mise à jour en suivant la procédure décrite dans le présent article.<br />
Il est essentiel de consulter les instructions de la rubrique <a href="plan-office-web-apps-server.md">Planification des mises à jour pour Office Web Apps Server</a> et d'établir un processus de mise à jour pour la batterie Office Web Apps Server.</td>
</tr>
</tbody>
</table>


## Avant de commencer

La liste la plus récente des mises à jour disponibles pour Office Web Apps Server peut être consultée sur le [blog Microsoft Office Updates](http://go.microsoft.com/fwlink/p/?linkid=280269) ainsi que sur le [Centre Technet de mises à jour pour Office, les serveurs Office et les produits associés](http://go.microsoft.com/fwlink/p/?linkid=280271).

Les mises à jour publiées pour Office Web Apps Server mettent à jour Office Web Apps Server et tous les modules linguistiques Office Web Apps Server installés. Il n'y a pas de mise à jour distincte pour les modules linguistiques Office Web Apps Server.

Dans le cadre du processus de mise à jour, vous devrez recréer la batterie Office Web Apps Server. Afin de préparer la recréation de la batterie Office Web Apps Server, consultez les propriétés de votre batterie Office Web Apps Server actuelle en exécutant la cmdlet Windows PowerShell**Get-OfficeWebAppsFarm**, et observez les paramètres pour [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps). Les paramètres utilisés pour **New-OfficeWebAppsFarm** doivent être identiques à ceux utilisés lors de la première installation de la batterie Office Web Apps Server.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><img src="images/JJ219459.note(Office.15).gif" title="Remarque" alt="Remarque" /><strong>Remarque :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Vous pouvez exécuter les tâches décrites dans cet article au moyen d'une souris, de raccourcis clavier ou d'entrées tactiles. Pour plus d'informations, consultez les ressources suivantes :
<ul>
<li><p><a href="http://go.microsoft.com/fwlink/p/?linkid=249150">Raccourcis clavier</a></p></li>
<li><p><a href="http://go.microsoft.com/fwlink/p/?linkid=249151">Entrées tactiles</a></p></li>
</ul></td>
</tr>
</tbody>
</table>


## Application des mises à jour logicielles dans une batterie Office Web Apps Server à serveur unique

Pour appliquer des mises à jour logicielles dans une batterie Office Web Apps Server à serveur unique, supprimez le Office Web Apps Server de la batterie, appliquez la mise à jour logicielle, puis recréez la batterie Office Web Apps Server. Si votre batterie Office Web Apps Server ne comporte qu'un seul serveur, les utilisateurs ne pourront pas utiliser Office Web Apps pendant que vous mettez le serveur à jour. Pensez donc à effectuer les mises à jour du Office Web Apps Server à une heure non critique ou pendant les heures de fermeture.

**Pour appliquer des mises à jour logicielles dans une batterie à serveur unique**

1.  Si la mise à jour n'a pas encore été téléchargée sur le Office Web Apps Server, téléchargez la mise à jour Office Web Apps Server à appliquer à partir du [Centre de téléchargement Microsoft](http://go.microsoft.com/fwlink/p/?linkid=280274).

2.  Sur le Office Web Apps Server sur lequel vous voulez appliquer la mise à jour logicielle, ouvrez l'invite Windows PowerShell en tant qu'administrateur et exécutez la commande suivante.
    
        Remove-OfficeWebAppsMachine

3.  Installez la mise à jour Office Web Apps Server sur ce serveur. Si vous y êtes invité, redémarrez le serveur.

4.  Ouvrez l'invite Windows PowerShell en tant qu'administrateur et exécutez la cmdlet **New-OfficeWebAppsFarm** pour recréer une batterie Office Web Apps Server. L'URL spécifiée pour **–InternalURL** est le nom du serveur qui exécute Office Web Apps Server (par exemple **http://Contoso-WAC**). Dans le cas présent, vous utilisez le même nom que celui de la batterie Office Web Apps Server précédente. Utilisez les mêmes paramètres supplémentaire que lors de la première création de la batterie Office Web Apps Server. Par exemple, le paramètre **–AllowHttp** configure la batterie pour qu'elle utilise le protocole HTTP et le paramètre **–EditingEnabled** autorise les modifications dans Office Web Apps lorsqu'il est utilisé conjointement avec SharePoint 2013. Le paramètre **–EditingEnabled** n'est pas utilisé par Lync Server 2013 ou Exchange Server 2013, car ces hôtes ne prennent pas en charge la modification.
    
    Le code de l'exemple suivant crée une batterie Office Web Apps Server appelée http://Contoso-WAC.
    
        New-OfficeWebAppsFarm -InternalURL "http://Contoso-WAC" -AllowHttp -EditingEnabled
    
    Des paramètres supplémentaires pour configurer les services de traduction, les serveurs proxy, la prise en charge des images clipart et les visionneuses en ligne sont décrits dans la rubrique [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps).

## Application des mises à jour logicielles dans une batterie Office Web Apps Server à plusieurs serveurs

Pour appliquer des mises à jour logicielles à une batterie Office Web Apps Server à serveurs multiples, vous devez d'abord supprimer l'un des serveurs du pool de l'équilibreur de charge et de la batterie, appliquer la mise à jour logicielle, puis créer une batterie Office Web Apps Server mise à jour. Vous supprimez et mettez ensuite à jour les serveurs restants de la batterie Office Web Apps Server, et les joignez à la nouvelle batterie mise à jour. Vous équilibrez la charge de trafic vers la nouvelle batterie lorsque vous avez suffisamment de serveurs dans celle-ci pour prendre en charge le trafic actuel. En ayant recours à ce processus de mise à jour, les utilisateurs peuvent ouvrir et modifier des documents dans Office Web Apps sans interruption.

**Pour appliquer des mises à jour logicielles dans une batterie à plusieurs serveurs**

1.  Téléchargez la mise à jour Office Web Apps Server à appliquer à partir du [Centre de téléchargement Microsoft](http://go.microsoft.com/fwlink/p/?linkid=280274) vers un emplacement réseau disponible pour la batterie Office Web Apps Server.

2.  Supprimez le serveur Office Web Apps Server sur lequel vous voulez appliquer la mise à jour logicielle du pool de l'équilibreur de charge.

3.  Sur ce serveur Office Web Apps Server, ouvrez l'invite Windows PowerShell en tant qu'administrateur et exécutez la commande suivante.
    
        Remove-OfficeWebAppsMachine

4.  Installez la mise à jour Office Web Apps Server sur ce serveur. Si vous y êtes invité, redémarrez le serveur.

5.  Ouvrez l'invite Windows PowerShell en tant qu'administrateur et créez une batterie Office Web Apps Server mise à jour en utilisant la cmdlet **New-OfficeWebAppsFarm**. L'URL spécifiée pour **–InternalURL** est le nom du serveur qui exécute Office Web Apps Server (par exemple **http://Contoso-WAC**). Dans le cas présent, vous utilisez le même nom que celui de la batterie Office Web Apps Server existante. Utilisez les mêmes paramètres supplémentaires que lors de la première création de la batterie Office Web Apps Server.Par exemple, le paramètre **–AllowHttp** configure la batterie pour qu'elle utilise le protocole HTTP et le paramètre **–EditingEnabled** autorise les modifications dans Office Web Apps lorsqu'il est utilisé conjointement avec SharePoint 2013. Le paramètre **–EditingEnabled** n'est pas utilisé par Lync Server 2013 ou Exchange Server 2013 , car ces hôtes ne prennent pas en charge la modification.
    
    Le code de l'exemple suivant crée une batterie Office Web Apps Server appelée http://Contoso-WAC.
    
        New-OfficeWebAppsFarm -InternalURL "http://Contoso-WAC" -AllowHttp -EditingEnabled
    
    Des paramètres supplémentaires pour configurer les services de traduction, les serveurs proxy, la prise en charge des images clipart et les visionneuses en ligne sont décrits dans la rubrique [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps).

6.  En fonction du nombre de serveurs présents dans la batterie Office Web Apps Server, équilibrez la charge du trafic vers la nouvelle batterie. Vous pouvez reporter cette étape jusqu'à ce que vous ayez plus de serveurs mis à jour dans la batterie.

7.  Effectuez les étapes suivantes pour chaque serveur restant de la batterie.
    
    1.  Supprimez le serveur Office Web Apps Server suivant du pool de l'équilibreur de charge.
    
    2.  Installez la mise à jour Office Web Apps Server sur ce serveur. Si vous y êtes invité, redémarrez le serveur.
    
    3.  Ouvrez l'invite Windows PowerShell en tant qu'administrateur et exécutez la commande suivante. Le paramètre **–MachineToJoin** ajoute le serveur actuel à une batterie Office Web Apps Server existante. Dans le cas présent, vous voulez ajouter le serveur à la batterie Office Web Apps Server mise à jour. Utilisez donc le nom de l'ordinateur de l'un des serveurs de la batterie Office Web Apps Server mise à jour.
        
            New-OfficeWebAppsMachine -MachineToJoin "server1.contoso.com"

## Voir aussi


[Remove-OfficeWebAppsMachine](https://docs.microsoft.com/en-us/powershell/module/officewebapps/remove-officewebappsmachine?view=officewebapps-ps)  
[New-OfficeWebAppsMachine](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsmachine?view=officewebapps-ps)  
[New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps)  
[Get-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/get-officewebappsfarm?view=officewebapps-ps)  


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
  

[](content-roadmap-for-office-web-apps-server.md)

