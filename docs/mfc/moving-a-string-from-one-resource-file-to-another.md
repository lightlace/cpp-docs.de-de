---
title: "Moving a String from One Resource File to Another"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strings [C++], moving between files"
  - "resource script files, moving strings"
  - "string editing, moving strings between resources"
  - "String editor, moving strings between files"
ms.assetid: 94f8ee81-9b4c-4788-ba95-68c58db38029
caps.latest.revision: 12
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Moving a String from One Resource File to Another
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### So verschieben Sie eine Zeichenfolge zwischen Ressourcenskriptdateien  
  
1.  Öffnen Sie die Zeichenfolgentabellen in beiden RC\-Dateien.  \(Weitere Informationen erhalten Sie unter [Öffnen einer Ressourcenskriptdatei außerhalb eines Projekts \(eigenständig\)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).\)  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC\-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Klicken Sie mit der rechten Maustaste auf die zu verschiebende Zeichenfolge, und wählen Sie im Kontextmenü den Befehl **Ausschneiden**.  
  
3.  Positionieren Sie den Cursor im Zielfenster **Zeichenfolgen\-Editor**.  
  
4.  Klicken Sie in der RC\-Datei, in die die Zeichenfolge verschoben werden soll, mit der rechten Maustaste, und wählen Sie **Einfügen** aus dem Kontextmenü.  
  
    > [!NOTE]
    >  Wenn **ID** oder **Wert** der verschobenen Zeichenfolge einen Konflikt mit einer vorhandenen **ID** bzw. einem **Wert** in der Zieldatei verursachen, wird entweder die **ID** oder der **Wert** der verschobenen Zeichenfolge geändert.  Wenn eine Zeichenfolge mit der gleichen **ID** vorhanden ist, ändert sich die **ID** der verschobenen Zeichenfolge.  Wenn eine Zeichenfolge mit dem gleichen **Wert** vorhanden ist, ändert sich der **Wert** der verschobenen Zeichenfolge.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten \(die die Common Language Runtime zum Ziel haben\) finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Anforderungen**  
  
 Win32  
  
## Siehe auch  
 [String Editor](../mfc/string-editor.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Anpassen von Fensterlayouts](../Topic/Customizing%20window%20layouts%20in%20Visual%20Studio.md)   
 [Zeichenfolgen](_win32_Strings)   
 [Informationen zu Zeichenfolgen](_win32_About_Strings_cpp)