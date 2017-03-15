---
title: "Zeichentests | Microsoft Docs"
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
ms.assetid: 376ba061-bae3-427e-9569-33fa5949a199
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Zeichentests
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 4.3.1** Die Zeichensätze, auf die von den `isalnum`\-, `isalpha`\-, `iscntrl`\-, `islower`\-, `isprint`\- und `isupper`\-Funktionen geprüft wird  
  
 Die folgende Liste beschreibt diese Funktionen, wie sie vom Microsoft C\-Compiler implementiert werden.  
  
|Funktion|Tests für|  
|--------------|---------------|  
|`isalnum`|Die Zeichen 0 bis 9, A\-Z, a\-z ASCII 48\-57, 65\-90, 97\-122|  
|`isalpha`|Die Zeichen A–Z, a–z ASCII 65–90, 97–122|  
|`iscntrl`|ASCII 0 –31, 127|  
|`islower`|Die Zeichen a\-z,ASCII 97\-122|  
|`isprint`|Die Zeichen A\-Z, a\-z, 0\-9, Satzzeichen, Leezeichen\-ASCII 32\-126|  
|`isupper`|Die Zeichen A–Z,ASCII 65\-90|  
  
## Siehe auch  
 [Bibliotheksfunktionen](../c-language/library-functions.md)