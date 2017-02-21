---
title: "Version Information Editor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.version.F1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Version Information editor, about Version Information editor"
  - "editors, Version Information"
  - "resource editors, Version Information editor"
ms.assetid: 772e6f19-f765-4cec-9521-0ad3eeb99f9b
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Version Information Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Versionsinformationen bestehen aus einer Firmen\- und einer Produkt\-ID, einer Produktseriennummer und Copyright\- und Markenbestimmungen. Mit dem Versionsinformations\-Editor können Sie diese Daten, die in der Versionsinformationsressource gespeichert sind, erstellen und warten. Die Versionsinformationsressource ist für eine Anwendung nicht erforderlich, sie stellt aber einen sinnvollen Ort dar, alle Informationen zusammenzuführen, die zur Identifizierung der Anwendung dienen. Versionsinformationen werden auch von Setup\-APIs verwendet.  
  
 Eine Versionsinformationsressource weist einen oberen Block und mindestens einen unteren Block auf: ein einzelner Block mit unveränderlichen Informationen oben und mindestens ein weiterer Versionsinformationsblock darunter \(für andere Sprachen und\/oder Zeichensätze\). Der obere Block weist sowohl editierbare Zahlenfelder als auch auswählbare Dropdownlisten auf. Die unteren Blöcke weisen nur editierbare Textfelder auf.  
  
> [!NOTE]
>  Der Windows\-Standard sieht nur eine Versionsressource mit dem Namen VS\_VERSION\_INFO vor.  
  
 Mithilfe des Versionsinformations\-Editors können Sie dies ausführen:  
  
-   [Bearbeiten einer Zeichenfolge in einer Versionsinformationsressource](../mfc/editing-a-string-in-a-version-information-resource.md)  
  
-   [Hinzufügen von Versionsinformationen für eine andere Sprache \(neuer Versionsinformationsblock\)](../mfc/adding-version-information-for-another-language.md)  
  
-   [Löschen eines Versionsinformationsblocks](../mfc/deleting-a-version-information-block.md)  
  
-   [Zugreifen auf Versionsinformationen aus dem Programm](../mfc/accessing-version-information-from-within-your-program.md)  
  
    > [!NOTE]
    >  Indem Sie im Versionsinformations\-Editor auf die rechte Maustaste klicken, können Sie in vielen Situationen ein Kontextmenü aufrufen, in dem ressourcenspezifische Befehle enthalten sind. Wenn Sie z. B. klicken, während Sie auf einen Blockheadereintrag zeigen, zeigt das Kontextmenü die Befehle „Neue Versionsblockinformationen“ und „Versionsblockinformationen löschen“ an.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Anforderungen  
 Win32  
  
## Siehe auch  
 [Resource Editors](../mfc/resource-editors.md)   
 [Menüs und weitere Ressourcen](http://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)