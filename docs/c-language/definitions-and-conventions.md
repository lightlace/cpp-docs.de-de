---
title: "Definitionen und Konventionen | Microsoft Docs"
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
  - "Definition von Nichtterminals"
ms.assetid: f9b3cf5f-6a7c-4a10-9b18-9d4a43efdaeb
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Definitionen und Konventionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bei Terminalen handelt es sich um Endpunkte in einer Syntaxdefinition.  Es ist keine andere Auflösung möglich.  Terminale enthalten den Satz reservierter Wörter und benutzerdefinierter Bezeichner.  
  
 Nichtterminale sind Platzhalter in der Syntax und werden an anderer Stelle in dieser Syntaxzusammenfassung definiert.  Definitionen können rekursiv sein.  
  
 Eine optionale Komponente wird durch das tiefgestellte "opt" angegeben.  Beispiel:  
  
```  
  
{ expression <SUB>opt</SUB> }  
```  
  
 gibt einen optionalen Ausdruck an, der in Klammern eingeschlossen wird.  
  
 Die Syntaxkonventionen verwenden verschiedene Schriftartattribute für unterschiedliche Syntaxkomponenten.  Die Symbole und die Schriftarten lauten wie folgt:  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|*nichtterminal*|Kursivschrift gibt Nichtterminale an.|  
|**const**|Fett formatierte Terminale sind literale, reservierte Symbole und Wörter, die wie gezeigt eingegeben werden müssen.  Bei Zeichen in diesem Kontext wird immer die Groß\-\/Kleinschreibung beachtet.|  
|opt|Nichtterminale, die von "opt" gefolgt werden, sind immer optional.|  
|Standardschriftart|Zeichen des in dieser Schriftart beschriebenen oder aufgeführten Satzes können als Terminals in C\-Anweisungen verwendet werden.|  
  
 Ein Doppelpunkt \(**:**\) nach einem Nichtterminal führt ihre Definition ein.  Alternative Definitionen werden in separaten Zeilen aufgeführt, außer wenn sie mit den Wörtern "one of" eingeleitet werden.  
  
## Siehe auch  
 [Syntax der Programmiersprache C \- Zusammenfassung](../c-language/c-language-syntax-summary.md)