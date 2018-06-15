---
title: Erweitert, Manifesttool, Konfigurationseigenschaften, Dialogfeld „&lt;Projektname&gt;-Eigenschaftenseiten“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCManifestTool.KeyFile
- VC.Project.VCManifestTool.UpdateFileHashes
- VC.Project.VCManifestTool.UpdateFileHashesSearchPath
- VC.Project.VCManifestTool.ValidateSignature
- VC.Project.VCManifestTool.KeyContainer
dev_langs:
- C++
ms.assetid: 3d587366-05ea-4956-a978-313069660735
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 47d4dc3ab325a7346d0e787a15d69d646896827d
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "33326936"
---
# <a name="advanced-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Erweitert, Manifesttool, Konfigurationseigenschaften, Dialogfeld „&lt;Projektname&gt;-Eigenschaftenseiten“
Verwenden Sie dieses Dialogfeld, um erweiterte Optionen für die Datei [Mt.exe](http://msdn.microsoft.com/library/aa375649) anzugeben.  
  
 Öffnen Sie die Eigenschaftenseiten für Ihr Projekt oder Ihr Eigenschaftenblatt, um auf das Dialogfeld „Eigenschaftenseite“ zuzugreifen. Erweitern Sie den Knoten **Manifesttool** unter **Konfigurationseigenschaften**, und klicken Sie dann auf **Erweitert**.  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Dateihashes aktualisieren**  
 Verwenden Sie die Option „/hashupdate“, um anzugeben, dass das Manifesttool den Hashwert der in den `<file>`-Elementen angegebenen Dateien berechnet, und aktualisieren Sie dann die Hashattribute mit dem berechneten Wert.  
  
 **Suchpfad für Dateihashes aktualisieren**  
 Gibt den Suchpfad für Dateien an, auf die in `<file>`-Elementen verwiesen wird. Diese Option verwendet auch die Option „/hashupdate“.  
  
## <a name="see-also"></a>Siehe auch  
 [\<file>-Element](/visualstudio/deployment/file-element-clickonce-application)   
 [ClickOnce Application Manifest (ClickOnce-Anwendungsmanifest)](/visualstudio/deployment/clickonce-application-manifest)   
 [Manifesttooleigenschaftenseiten](../ide/manifest-tool-property-pages.md)   
 [Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md)   