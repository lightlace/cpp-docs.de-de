---
title: "Linkertoolfehler LNK1561 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1561"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1561"
ms.assetid: cb0b709b-7c9c-4496-8a4e-9e1e4aefe447
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Linkertoolfehler LNK1561
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Einstiegspunkt muss definiert sein  
  
 Der Linker konnte keinen Einstiegspunkt finden.  Möglicherweise war eine DLL\-Verknüpfung beabsichtigt. In diesem Fall sollten Sie die Verknüpfung mit der [\/DLL](../../build/reference/dll-build-a-dll.md)\-Option durchführen.  Unter Umständen wurde aber auch vergessen, den Namen des Einstiegspunktes festlegen; führen Sie die Verknüpfung mit der [\/ENTRY](../../build/reference/entry-entry-point-symbol.md)\-Option durch.  
  
 Andernfalls sollte eine der Funktionen **main**, **wmain**, `WinMain` oder **wMain** in den Code aufgenommen werden.  
  
 Wenn Sie bei Verwendung von [LIB](../../build/reference/lib-reference.md) versuchen, eine DLL zu erstellen, könnte eine Fehlerursache darin liegen, dass Sie eine DEF\-Datei angegeben haben.  Entfernen Sie in diesem Fall die DEF\-Datei aus dem Build.  
  
 Im folgenden Beispiel wird LNK1561 generiert:  
  
```  
// LNK1561.cpp  
// LNK1561 expected  
int i;  
// add a main function to resolve this error  
```