---
title: Manifest Tool Eingabe- und Ausgabeeigenschaften (Visual C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCManifestTool.OutputManifestFile
- VC.Project.VCManifestTool.InputResourceManifests
- VC.Project.VCManifestTool.EmbedManifest
- VC.Project.VCManifestTool.AdditionalManifestFiles
- VC.Project.VCManifestTool.DependencyInformationFile
- VC.Project.VCManifestTool.OutputResourceManifest
- VC.Project.VCManifestTool.GenerateCatalogFiles
dev_langs: C++
ms.assetid: a8bb20f6-7ace-45ca-bab0-b4f4a5caf170
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 77137e9bc0a4af60080234aac85afa59034d2c6a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="input-and-output-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Eingabe und Ausgabe, Tools, Konfigurationseigenschaften, Manifest &lt;Projektname&gt; Eigenschaftenseiten (Dialogfeld)
Verwenden Sie dieses Dialogfeld zum Angeben von Eingabe- und Optionen für [Mt.exe](http://msdn.microsoft.com/library/aa375649).  
  
 Öffnen Sie diese Eigenschaftenseiten-Dialogfeld für den Zugriff auf die Eigenschaftenseiten für das Projekt oder das Eigenschaftenblatt. Erweitern Sie die **Manifesttool** Knoten unter **Konfigurationseigenschaften**, und wählen Sie dann **ein- und Ausgabe**.  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Zusätzliche Manifestdateien**  
 Verwendet die **/manifest** Option, um die vollständigen Pfade der zusätzliche Manifestdateien, die die Manifesttool verarbeitet oder Merge anzugeben. Vollständige Pfade werden durch ein Semikolon getrennt.  
  
 **Eingaberessource-Manifeste**  
 Verwendet die **inputresource** Option aus, um den vollständigen Pfad einer Ressource vom Typ RT_MANIFEST anzugeben, die das manifest Tool angeben. Der Pfad kann die angegebenen Ressourcen-ID folgen. Zum Beispiel:  
  
 `dll_with_manifest.dll;#1`  
  
 Die Ressourcen-ID ist optional und standardmäßig CREATEPROCESS_MANIFEST_RESOURCE_ID in winuser.h standardmäßig.  
  
 **Manifest einbetten**  
 **Ja** gibt an, dass das Projektsystem die Anwendungsmanifestdatei in die Assembly eingebettet wird.  
  
 **Nicht** gibt an, dass das Projektsystem die Anwendungsmanifestdatei als eigenständige Datei erstellen.  
  
 **Ausgabemanifestdatei an**  
 Gibt den Namen der der Ausgabemanifestdatei an. Diese Eigenschaft ist optional, wenn Sie nur eine Manifestdatei vom Manifesttool bearbeitet wird.  
  
 **Manifestressource-Datei**  
 Gibt die Ausgabe mit dem Ressourcendateien verwendet, um das Manifest in die Projektausgabe eingebettet.  
  
 **Katalogdateien generieren**  
 Verwendet die **makecdfs** Option aus, um anzugeben, dass das manifest generiert das Tool Katalog-Definitionsdateien (CDF-Dateien), die verwendet werden, um Kataloge zu machen.  
  
 **Generieren des Manifests von ManagedAssembly**  
 Generiert ein Manifest aus einer verwalteten Assembly. (**- Managedassemblyname:***Datei*).  
  
 **Abhängigkeitselement unterdrücken**  
 Verwendet die **- Managedassembly** Option. Dieses Tag unterdrückt die Generierung der Abhängigkeitselemente im endgültigen Manifest.  
  
 **Von Kategorietags zu generieren**  
 Verwendet die **- Managedassembly** Option. Dieses Tag bewirkt, dass die Kategorietags generiert werden soll.  
  
 **Aktivieren der DPI-Ausführung**  
 Gibt an, ob die Anwendung DPI-fähig ist. Standardmäßig ist die Einstellung **Ja** für MFC-Projekte und **keine** andernfalls, da MFC-Projekten in DPI-Ausführung erstellt haben. Sie können die Einstellung zu überschreiben, **Ja** , wenn Sie Code zur Behandlung von unterschiedlichen DPI-Einstellungen hinzufügen. Ihre Anwendung möglicherweise fuzzy oder kleine, wenn Sie es als DPI-bewusst festlegen, wenn es nicht angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [ClickOnce-Anwendungsmanifest](/visualstudio/deployment/clickonce-application-manifest)   
 [Manifesttool-Eigenschaftenseiten](../ide/manifest-tool-property-pages.md)   
 [Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md)   