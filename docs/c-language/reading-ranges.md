---
title: "Lesen von Bereichen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
ms.assetid: 99de29ce-ab14-46f4-97e1-2081fd996b53
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Lesen von Bereichen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 4.9.6.2** Die Interpretation eines Bindestriches \(–\), der weder das erste noch das letzte Zeichen in der Suchliste der % \[\-Konvertierung in der `fscanf`\-Funktion ist  
  
 Die folgende Zeile  
  
```  
fscanf( fileptr, "%[A-Z]", strptr);  
```  
  
 liest eine beliebige Anzahl von Zeichen im Bereich von A\-Z in der Zeichenfolge, auf die `strptr` zeigt.  
  
## Siehe auch  
 [Bibliotheksfunktionen](../c-language/library-functions.md)