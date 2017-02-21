---
title: "Previewing Resources | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.resvw.resource.previewing"
  - "vs.resvw.resource.previewing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio], viewing"
  - "resource previews"
  - "code, viewing"
ms.assetid: d6abda66-0e2b-4ac3-a59a-a57b8c6fb70b
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Previewing Resources
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Durch die Vorschau auf Ressourcen können Sie eine grafische Ressource betrachten, ohne sie zu öffnen.  Die Vorschaufunktion ist auch nach der Kompilierung ausführbarer Dateien hilfreich, da die Ressourcenbezeichner in Ziffern geändert werden.  Da diese numerischen Bezeichner oft nicht genügend Informationen liefern, können Sie sie mittels der Ressourcenvorschau schnell identifizieren.  
  
 In einer Vorschau kann das Layout der folgenden Ressourcentypen angezeigt werden:  
  
-   Bitmap  
  
-   Dialogfeld  
  
-   Symbol  
  
-   Menü  
  
-   Cursor  
  
-   Symbolleiste  
  
 Für Ressourcen, wie Zugriffstasten, Manifeste, Zeichenfolgentabellen und Versionsinformationen, ist die visuelle Vorschau nicht verfügbar.  
  
### So zeigen Sie eine Ressourcenvorschau an  
  
1.  Wählen Sie die Ressource in der [Ressourcenansicht](../windows/resource-view-window.md) oder in einem Dokumentfenster aus, z. B. **IDD\_ABOUTBOX**.  
  
     **Hinweis** Wenn das Projekt noch keine RC\-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Klicken Sie im [Eigenschaftenfenster](../Topic/Properties%20Window.md) auf die Schaltfläche **Eigenschaftenseiten**.  
  
     \- oder \-  
  
3.  Klicken Sie im Menü **Ansicht** auf die Option **Eigenschaftenseiten**.  
  
     Die Eigenschaftenseite der Ressource wird mit einer Vorschau der Ressource geöffnet.  Anschließend können Sie mit der NACH\-OBEN\- bzw. NACH\-UNTEN\-TASTE durch die Strukturansicht in der Ressourcenansicht oder im Dokumentfenster navigieren.  Die **Eigenschaftenseite** bleibt geöffnet und zeigt jede Ressource an, die den Fokus besitzt und die die Vorschaufunktion unterstützt.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Anforderungen**  
  
 Win32  
  
## Siehe auch  
 [How to: Open a Resource Script File Outside of a Project \(Standalone\)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)   
 [Resource Editors](../mfc/resource-editors.md)