---
title: "Adding Formatting or Special Characters to a String"
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
  - "special characters, adding to strings"
  - "ASCII characters, adding to strings"
  - "strings [C++], formatting"
  - "strings [C++], special characters"
ms.assetid: c40f394a-8b2c-4896-ab30-6922863ddbb5
caps.latest.revision: 11
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Adding Formatting or Special Characters to a String
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### So fügen Sie einer Zeichenfolge Formatierung oder Sonderzeichen hinzu  
  
1.  Öffnen Sie die Zeichenfolgentabelle, indem Sie in der [Ressourcenansicht](../windows/resource-view-window.md) auf das zugehörige Symbol doppelklicken.  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC\-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Markieren Sie die gewünschte Zeichenfolge.  
  
3.  Fügen Sie dem Text im Feld **Beschriftung** des [Eigenschaftenfensters](../Topic/Properties%20Window.md) eine der nachfolgend aufgeführten standardmäßigen Escape\-Sequenzen hinzu, und drücken Sie die **EINGABETASTE**.  
  
    |Ziel|Eingabe|  
    |----------|-------------|  
    |Zeilenwechsel|\\n|  
    |Wagenrücklauf|\\r|  
    |Registerkarte|\\t|  
    |Umgekehrter Schrägstrich \(\\\)|\\\\|  
    |ASCII\-Zeichen|\\ddd \(oktale Darstellung\)|  
    |Warnton \(Gong\)|\\a|  
  
> [!NOTE]
>  Der Zeichenfolgen\-Editor unterstützt nicht den vollständigen Satz von ASCII\-Zeichen in Escape\-Sequenzen.  Sie können lediglich die oben angegebenen Zeichen verwenden.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten \(die die Common Language Runtime zum Ziel haben\) finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Anforderungen**  
  
 Win32  
  
## Siehe auch  
 [String Editor](../mfc/string-editor.md)   
 [Zeichenfolgen](_win32_Strings)   
 [Informationen zu Zeichenfolgen](_win32_About_Strings_cpp)