---
title: Eingabe- und Ausgabeeigenschaften des Manifesttools (Visual C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCManifestTool.OutputManifestFile
- VC.Project.VCManifestTool.InputResourceManifests
- VC.Project.VCManifestTool.EmbedManifest
- VC.Project.VCManifestTool.AdditionalManifestFiles
- VC.Project.VCManifestTool.DependencyInformationFile
- VC.Project.VCManifestTool.OutputResourceManifest
- VC.Project.VCManifestTool.GenerateCatalogFiles
dev_langs:
- C++
ms.assetid: a8bb20f6-7ace-45ca-bab0-b4f4a5caf170
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 15be7636188bb670febd7875974d683c1d78360f
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "33331557"
---
# <a name="input-and-output-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Eingabe und Ausgabe, Manifesttool, Konfigurationseigenschaften, Dialogfeld „&lt;Projektname&gt;-Eigenschaftenseiten“
Verwenden Sie dieses Dialogfeld, um Eingabe- und Ausgabeoptionen für die Datei [Mt.exe](http://msdn.microsoft.com/library/aa375649) anzugeben.  
  
 Öffnen Sie die Eigenschaftenseiten für Ihr Projekt oder Ihr Eigenschaftenblatt, um auf das Dialogfeld „Eigenschaftenseite“ zuzugreifen. Erweitern Sie den Knoten **Manifesttool** unter **Konfigurationseigenschaften**, und klicken Sie dann auf **Eingabe und Ausgabe**.  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Zusätzliche Manifestdateien**  
 Verwendet die Option **/manifest**, um die vollständigen Pfade von zusätzlichen Manifestdateien anzugeben, die das Manifesttool verarbeitet oder zusammenführt. Vollständige Pfade werden durch Semikolons getrennt.  
  
 **Ressourcenmanifeste eingeben**  
 Verwendet die Option **/inputresource**, um den vollständigen Pfad einer Ressource vom Typ RT_MANIFEST anzugeben, die in das Manifesttool eingegeben wird. Dem Pfad kann die angegebene Ressourcen-ID folgen. Zum Beispiel:  
  
 `dll_with_manifest.dll;#1`  
  
 Die Ressourcen-ID ist optional und lautet standardmäßig CREATEPROCESS_MANIFEST_RESOURCE_ID in „winuser.h“.  
  
 **Manifest einbetten**  
 **Ja** gibt an, dass das Projektsystem die Anwendungsmanifestdatei in die Assembly einbettet.  
  
 **Nein** gibt an, dass das Projektsystem die Anwendungsmanifestdatei als eigenständige Datei erstellt.  
  
 **Manifestdatei ausgeben**  
 Gibt den Namen der Ausgabemanifestdatei an. Diese Eigenschaft ist optional, wenn nur eine Manifestdatei mit dem Manifesttool bearbeitet wird.  
  
 **Manifestressourcendatei**  
 Gibt die Ausgaberessourcendateien an, die verwendet werden, um das Manifest in die Projektausgabe einzubetten.  
  
 **Katalogdateien generieren**  
 Verwendet die Option **/makecdfs**, um anzugeben, dass das Manifesttool die Katalogdefinitionsdateien (CDF-Dateien) generiert, die zum Erstellen von Katalogen verwendet werden.  
  
 **Manifest aus einer verwalteten Assembly generieren**  
 Generiert ein Manifest aus einer verwalteten Assembly. (**-managedassemblyname:***file*).  
  
 **Abhängigkeitselement unterdrücken**  
 Wird mit der Option **-managedassembly** verwendet. Dieses Tag unterdrückt die Generierung von Abhängigkeitselementen im endgültigen Manifest.  
  
 **Kategorietags generieren**  
 Wird mit der Option **-managedassembly** verwendet. Durch dieses Tag werden die Kategorietags generiert.  
  
 **DPI aktivieren**  
 Gibt an, ob die Anwendung DPI-fähig ist. Für MFC-Projekte ist diese Einstellung standardmäßig auf **Ja** festgelegt, andernfalls ist **Nein** festgelegt, da nur MFC-Projekte über integrierte DPI-Unterstützung verfügen. Sie können die Einstellung auf **Ja** festlegen, indem Sie Code hinzufügen, um verschiedene DPI-Einstellungen zu verarbeiten. Wenn Sie Ihre Anwendung auf DPI-fähig einstellen und sie nicht DPI-fähig ist, wird sie möglicherweise verschwommen oder klein angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [ClickOnce Application Manifest (ClickOnce-Anwendungsmanifest)](/visualstudio/deployment/clickonce-application-manifest)   
 [Manifesttooleigenschaftenseiten](../ide/manifest-tool-property-pages.md)   
 [Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md)   