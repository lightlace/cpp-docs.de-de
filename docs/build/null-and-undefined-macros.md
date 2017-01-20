---
title: "NULL-Makros und undefinierte Makros"
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
helpviewer_keywords: 
  - "Makros, NULL und nicht definiert"
  - "NMAKE (Programm), NULL-Makros"
  - "NMAKE (Programm), Undefinierte Makros"
  - "NULL-Makros in NMAKE"
  - "Undefinierte Makros und NMAKE"
ms.assetid: 1db4611a-1755-4328-b00f-d35365af8b6c
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# NULL-Makros und undefinierte Makros
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

NULL\-Makros und undefinierte Makros werden zu NULL\-Zeichenfolgen erweitert. Ein Makro, das als NULL\-Zeichenfolge definiert ist, wird in Präprozessorausdrücken als definiertes Makro aufgefasst.  Um ein Makro als NULL\-Zeichenfolge zu definieren, werden nach dem Gleichheitszeichen \(**\=**\) keine anderen Zeichen außer Leerzeichen oder Tabstopps in einer Befehlszeile oder Befehlsdatei eingegeben, und die NULL\-Zeichenfolge oder Definition wird in doppelte Anführungszeichen \(**" "**\) eingeschlossen.  Um Makrodefinitionen aufzuheben, wird **\!UNDEF** verwendet. Weitere Informationen finden Sie unter [Direktiven für den Präprozessorlauf eines Makefiles](../build/makefile-preprocessing-directives.md).  
  
## Siehe auch  
 [Definieren eines NMAKE\-Makros](../build/defining-an-nmake-macro.md)