---
title: "Linkertoolfehler LNK2023"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2023"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2023"
ms.assetid: c99e35a8-739a-4a20-a715-29b8c3744703
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK2023
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Schlecht\-DLL\- oder \-Einstiegspunkt\- \<DLL oder Einstiegspunkt\>  
  
 Der Linker lädt eine falsche Version von msobj90.dll.  Stellen Sie sicher, dass link.exe und msobj90.dll im Pfad dieselbe Version haben.  
  
 Möglicherweise ist eine Abhängigkeit von msobj90.dll nicht vorhanden.  Die Liste der Abhängigkeiten für msobj90.dll lautet:  
  
-   Msvcr90.dll  
  
-   Kernel32.dll  
  
 Überprüfen Sie, ob auf dem Computer andere, eventuell nicht mehr aktuelle Kopien von msobj90.dll vorhanden sind.