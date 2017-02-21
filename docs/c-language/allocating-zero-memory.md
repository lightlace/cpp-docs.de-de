---
title: "Nullspeicherbelegung | Microsoft Docs"
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
  - "Speicherreservierung, Nullspeicher"
  - "Nullspeicher"
ms.assetid: 768f2ab9-83a1-4887-8eb5-c094c18489a8
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Nullspeicherbelegung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 4.10.3** Das Verhalten der `calloc`\-, `malloc`\- oder `realloc`\-Funktion, wenn die angeforderte Größe Null ist  
  
 Die `calloc`\-, `malloc`\- und `realloc`\-Funktionen akzeptieren Null als Argument.  Es wird kein physischer Arbeitsspeicher belegt, jedoch wird ein gültiger Zeiger zurückgegeben, und der Speicherblock kann später durch "realloc" geändert werden.  
  
## Siehe auch  
 [Bibliotheksfunktionen](../c-language/library-functions.md)