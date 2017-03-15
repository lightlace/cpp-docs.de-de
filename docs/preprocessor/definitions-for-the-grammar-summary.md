---
title: "Definitionen f&#252;r die Grammatikzusammenfassung | Microsoft Docs"
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
  - "Präprozessor"
  - "Präprozessor, Definitionen"
ms.assetid: cc752dc8-6f4e-4347-a556-e0d9ef4c46bd
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Definitionen f&#252;r die Grammatikzusammenfassung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bei Terminalen handelt es sich um Endpunkte in einer Syntaxdefinition.  Es ist keine andere Auflösung möglich.  Terminale enthalten den Satz reservierter Wörter und benutzerdefinierter Bezeichner.  
  
 Bei Nichtterminalen handelt es sich um Platzhalter in der Syntax.  Die meisten sind an anderer Stelle in dieser Syntaxzusammenfassung definiert.  Definitionen können rekursiv sein.  Die folgenden Nichtterminale werden in der [Zusammenfassung der Grammatik](../misc/grammar-summary-cpp.md) der *C\+\+\-Programmiersprachenreferenz* definiert:  
  
 `constant`, *konstanter Ausdruck*, *Bezeichner*, *Schlüsselwort*, `operator`, `punctuator`  
  
 Eine optionale Komponente wird durch das tiefgestellte "opt" angegeben.  Beispielsweise gibt folgende Komponente einen optionalen Ausdruck an, der in geschweiften Klammern eingeschlossen ist:  
  
 **{** *expression*opt **}**  
  
## Siehe auch  
 [Grammatikzusammenfassung](../preprocessor/grammar-summary-c-cpp.md)