---
title: Set-OfficeWebAppsMachine
TOCTitle: Set-OfficeWebAppsMachine
ms:assetid: aeba2638-be88-4030-80fe-7e4bcd30309b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ219448(v=office.15)
ms:contentKeyID: 49645233
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Set-OfficeWebAppsMachine

 

_**Sapplique à :**Office Web Apps Server_

_**Dernière rubrique modifiée :**2015-03-09_

Modifie les paramètres du serveur actuel inclus dans une batterie de serveurs Office Web Apps Server.

## Syntaxe

    Set-OfficeWebAppsMachine [-Confirm [<SwitchParameter>]] [-Master <String>] [-Roles <String[]>] [-WhatIf [<SwitchParameter>]]

## Description détaillée

La cmdlet **Set-OfficeWebAppsMachine**permet de modifier les paramètres du serveur actuel inclus dans une batterie Office Web Apps Server. Ces paramètres comprennent les rôles joués par le serveur actuel et le serveur maître désigné pour la batterie.

## Paramètres


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Paramètre</th>
<th>Obligatoire</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Confirm</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Vous demande confirmation avant d’exécuter la commande. Pour plus d’informations, entrez la commande suivante : <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Master</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String</p></td>
<td><p></p>
<p>Spécifie le serveur qui stocke les fichiers de configuration de batterie maître.</p>
<p>Si vous définissez le serveur local en tant que maître, vous devez exécuter <strong>Set-OfficeWebAppsMachine -Master</strong> sur tous les serveurs restants dans la batterie Office Web Apps Server afin qu'ils pointent vers le nouveau maître.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Roles</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.String[]</p></td>
<td><p>Spécifie la liste des rôles serveur à attribuer au serveur local, séparés par des virgules.</p>
<p>Les types de rôles sont les suivants :</p>
<p><strong>All</strong></p>
<p><strong>FrontEnd</strong></p>
<p><strong>WordBackEnd</strong></p>
<p><strong>ExcelBackEnd</strong></p>
<p><strong>PowerPointBackEnd</strong></p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Ff431682.important(Office.15).gif" title="Important" alt="Important" /><strong>Important :</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>En guise de meilleure pratique, il est recommandé que tous les serveurs d'une batterie de serveurs Office Web Apps Server exécutent tous les rôles. L'affectation de rôles ne s'avère pas utile tant que la batterie de serveurs Office Web Apps Server ne contient pas une cinquantaine de serveurs.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>WhatIf</strong></p></td>
<td><p>Facultatif</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Affiche un message qui explique l’effet de la commande au lieu de l’exécuter. Pour plus d’informations, entrez la commande suivante : <strong>get-help about_commonparameters</strong></p></td>
</tr>
</tbody>
</table>


## Types d’entrées

## Types de retours

## Exemple

\------------------EXEMPLE 1---------------------

    (Get-OfficeWebAppsFarm).Machines

Cet exemple montre les rôles joués par chaque serveur dans la batterie Office Web Apps Server.

\------------------EXEMPLE 2---------------------

    Set-OfficeWebAppsMachine -Roles FrontEnd

Cet exemple montre comment configurer le serveur actuel en tant que serveur frontal.

\------------------EXEMPLE 3---------------------

    Set-OfficeWebAppsMachine -Roles All

Cet exemple montre comment configurer le serveur actuel afin d'héberger tous les rôles.

## Voir aussi


[Get-OfficeWebAppsMachine](get-officewebappsmachine.md)  
[New-OfficeWebAppsMachine](new-officewebappsmachine.md)  
[Remove-OfficeWebAppsMachine](remove-officewebappsmachine.md)  


[Feuille de route de contenu pour Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Déployer l'infrastructure : Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

