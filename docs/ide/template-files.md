---
title: "Vorlagendateien | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Benutzerdefinierte Assistenten, Vorlagendateien"
  - "Dateien [C++], Erstellt durch einen benutzerdefinierten Assistenten"
  - "Vorlagen [C++], Für Assistenten"
ms.assetid: 48fae3d8-3a53-4f62-8010-144c5ffe334e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Vorlagendateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bei den Vorlagen, aus denen ein Assistent gebildet wird, handelt es sich um eine Zusammenstellung von Textdateien, die einige [einfache Direktiven](../ide/template-directives.md) enthalten und entsprechend den Benutzereingaben analysiert, gerendert und anschließend dem neuen Projekt hinzugefügt werden.  Die entsprechenden Informationen zum Analysieren der Vorlagen werden durch den direkten Zugriff auf die Symboltabelle der Assistentensteuerung ermittelt.  
  
 Beim folgenden Beispiel handelt es sich um eine sehr einfache Vorlagendatei für einen Assistenten, der den Benutzer auffordert, zwischen A und B auszuwählen.  
  
## Beispiel  
  
```  
This file has been created by My Custom wizard.  
You selected:  
[!if TYPE_A]  
Type A  
[!else]  
Type B  
[!endif]  
The name of this project is [!output PROJECT_NAME].root.cpp:  
```  
  
 Wenn der Benutzer "Type B" auswählt, wird diese Vorlage folgendermaßen gerendert:  
  
  **Diese Datei wurde vom benutzerdefinierten Assistenten erstellt.  Sie haben Folgendes ausgewählt:**  
**Typ B**  
**Der Name dieses Projekts lautet "MyApp8".**    
## Output  
  
```  
This file has been created by My Custom wizard.  
You selected:  
Type B  
The name of this project is MyApp8.  
```  
  
 **Hinweis** Die im obigen Beispiel verwendete Syntax ist neu in Visual C\+\+ .NET.  Die Syntax früherer Visual C\+\+\-Versionen wird in Visual C\+\+ .NET nicht unterstützt.  
  
## Siehe auch  
 [Für den Assistenten erstellte Dateien](../ide/files-created-for-your-wizard.md)   
 [Benutzerdefinierter Assistent](../ide/custom-wizard.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)   
 [INF\-Vorlagendatei](../ide/templates-inf-file.md)