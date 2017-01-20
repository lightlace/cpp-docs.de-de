---
title: "Nullspeicherbelegung"
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
helpviewer_keywords: 
  - "Speicherreservierung, Nullspeicher"
  - "Nullspeicher"
ms.assetid: 768f2ab9-83a1-4887-8eb5-c094c18489a8
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Nullspeicherbelegung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 4.10.3** Das Verhalten der `calloc`\-, `malloc`\- oder `realloc`\-Funktion, wenn die angeforderte Größe Null ist  
  
 Die `calloc`\-, `malloc`\- und `realloc`\-Funktionen akzeptieren Null als Argument.  Es wird kein physischer Arbeitsspeicher belegt, jedoch wird ein gültiger Zeiger zurückgegeben, und der Speicherblock kann später durch "realloc" geändert werden.  
  
## Siehe auch  
 [Bibliotheksfunktionen](../c-language/library-functions.md)