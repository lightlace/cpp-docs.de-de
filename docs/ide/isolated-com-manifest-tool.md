---
title: Manifesttool isolierte COM-Eigenschaften (Visual C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCManifestTool.RegistrarScriptFile
- VC.Project.VCManifestTool.ComponentFileName
- VC.Project.VCManifestTool.TypeLibraryFile
- VC.Project.VCManifestTool.ReplacementsFile
dev_langs:
- C++
ms.assetid: 457582b8-cfde-49c0-92e3-3a6b9e8c08eb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fe2098c4caead6ebc9ad4747354ae96f093f2c91
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="isolated-com-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Isolierte COM, Manifesttool, Konfigurationseigenschaften, &lt;Projektname&gt; Eigenschaftenseiten (Dialogfeld)
Mithilfe dieses Dialogfelds an **Isolated COM** Optionen für [Mt.exe](http://msdn.microsoft.com/library/aa375649).  
  
 Öffnen Sie diese Eigenschaftenseiten-Dialogfeld für den Zugriff auf die Eigenschaftenseiten für das Projekt oder das Eigenschaftenblatt. Erweitern Sie die **Manifesttool** Knoten unter **allgemeine Eigenschaften**, und wählen Sie dann **Isolated COM**.  
  
## <a name="task-list"></a>Aufgabenliste  
  
-   [Vorgehensweise: Erstellen von isolierten Anwendungen zur Verwendung von COM-Komponenten](../build/how-to-build-isolated-applications-to-consume-com-components.md)  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Typbibliotheksdatei an**  
 Verwendet die Option/tlb um den Namen der Typbibliotheksdatei (TLB-Datei) anzugeben, die zum Generieren der Manifestdatei Manifesttool verwenden.  
  
 **Registrierungsskriptdatei**  
 Verwendet die Option legt den Namen der Registrierungsskriptdatei (.rgs-Datei) an, die zum Generieren der Manifestdatei Manifesttool verwenden.  
  
 **Dateiname der Komponente**  
 Verwendet die/DLL-Option den Namen der Ressource an, die das manifest Tool generiert. Geben Sie einen Wert für diese Eigenschaft bei der Werte für entweder **Typbibliotheksdatei** oder **Registrierungsskriptdatei** angegeben werden.  
  
 **Ersetzungsdatei**  
 Verwendet die Option/replacements fest, geben Sie den vollständigen Pfad zur Datei, die Werte für ersetzbare Zeichenfolgen in der RGS-Datei enthält.  
  
## <a name="see-also"></a>Siehe auch  
 [Isolierte Anwendungen](http://msdn.microsoft.com/library/aa375190)   
 [ClickOnce-Anwendungsmanifest](/visualstudio/deployment/clickonce-application-manifest)   
 [Manifesttool-Eigenschaftenseiten](../ide/manifest-tool-property-pages.md)   
 [Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md)   