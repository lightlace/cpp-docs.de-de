---
title: "Linkertoolwarnung LNK4217 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4217"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4217"
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Linkertoolwarnung LNK4217
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lokal definiertes Symbol 'Symbol' wurde in Funktion 'Funktion' importiert  
  
 [\_\_declspec\(dllimport\)](../../cpp/dllexport-dllimport.md) wurde für ein Symbol angegeben, obwohl das Symbol lokal definiert ist.  Entfernen Sie den `__declspec`\-Modifizierer, um diese Warnung zu vermeiden.  
  
 `symbol` entspricht dem im Bild definierten Symbolnamen.  `function` steht für die Funktion, durch die das Symbol importiert wird.  
  
 Diese Warnung wird nicht angezeigt, wenn Sie zum Kompilieren die Option [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) verwenden  
  
 LNK4217 kann auch bei dem Versuch auftreten, zwei Module miteinander zu verknüpfen, wenn stattdessen das zweite Modul mit der Importbibliothek des ersten Moduls kompiliert werden sollte.  
  
```  
// LNK4217.cpp  
// compile with: /LD  
#include "windows.h"  
__declspec(dllexport) void func(unsigned short*) {}  
```  
  
 und anschließend  
  
```  
// LNK4217b.cpp  
// compile with: /c  
#include "windows.h"  
__declspec(dllexport) void func(unsigned short*) {}  
```  
  
 Der Versuch, diese beiden Module miteinander zu verknüpfen, führt zur Warnmeldung LNK4217. Kompilieren Sie stattdessen das zweite Beispiel mit der Importbibliothek des ersten Beispiels.