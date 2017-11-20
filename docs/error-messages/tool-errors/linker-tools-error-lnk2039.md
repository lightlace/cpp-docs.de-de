---
title: "Linkertoolfehler LNK2039 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2039"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2039"
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# Linkertoolfehler LNK2039
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verweisklassentyp '\<importieren,\>' der in another.obj definiert wird; er sollte entweder importiert bzw. definiert sind, aber nicht beide  
  
 Die Verweisklasse '\<`type`\>' importiert, im angegebenen OBJ\-Datei ist aber ebenfalls in einer OBJ\-Datei anderen definiert.  Diese Bedingung kann zu Laufzeitfehlern oder anderes unerwartetes Verhalten verursachen.  
  
### So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass '`type`' in der anderen OBJ\-Datei und der Überprüfung definiert werden muss, ob sie von der WINMD\-Datei importiert werden muss.  
  
2.  Entfernen Sie entweder die Definition oder den Import.  
  
## Siehe auch  
 [Fehler und Warnungen der Linkertools](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)   
 [Linkertoolfehler LNK1332](../../error-messages/tool-errors/linker-tools-error-lnk1332.md)