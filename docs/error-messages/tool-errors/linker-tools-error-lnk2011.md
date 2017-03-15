---
title: "Linkertoolfehler LNK2011 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2011"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2011"
ms.assetid: 04991ef5-49d5-46c7-8eee-a9d1d3fc541e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Linkertoolfehler LNK2011
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vorkompiliertes Objekt nicht eingebunden; Datei möglicherweise nicht ausführbar  
  
 Bei Verwendung vorkompilierter Header erfordert LINK, dass alle mit vorkompilierten Headern erstellten Objektdateien verknüpft werden.  Wenn Sie eine Quelldatei zum Generieren eines vorkompilierten Headers mit anderen Quelldateien verwenden, muss neben dem vorkompilierten Header auch die erstellte Objektdatei einbezogen werden.  
  
 Wenn Sie z. B. eine Datei mit dem Namen **STUB.cpp** kompilieren, um einen vorkompilierten Header zur Verwendung mit anderen Quelldateien zu erstellen, sollten Sie eine Verknüpfung mit **STUB.obj** herstellen, da andernfalls dieser Fehler ausgegeben wird.  In den folgenden Befehlszeilen wird Zeile 1 dazu verwendet, den vorkompilierten Header **COMMON.pch** zu erstellen, der in den Zeilen 2 und 3 von **PROG1.cpp** und **PROG2.cpp** verwendet wird.  Die Datei **STUB.cpp** enthält lediglich `#include`\-Zeilen \(die gleichen `#include`\-Zeilen wie in **PROG1.cpp** und **PROG2.cpp**\) und wird nur zum Generieren von vorkompilierten Headern verwendet.  In der letzten Zeile muss **STUB.obj** verknüpft werden, um LNK2011 zu vermeiden.  
  
```  
cl /c /Yccommon.h stub.cpp  
cl /c /Yucommon.h prog1.cpp  
cl /c /Yucommon.h prog2.cpp  
link /out:prog.exe stub.obj prog1.obj prog2.obj  
```