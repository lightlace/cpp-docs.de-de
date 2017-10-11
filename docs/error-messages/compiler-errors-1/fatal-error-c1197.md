---
title: Schwerwiegender Fehler C1197 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1197
dev_langs:
- C++
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d0eb3ab152e9299d47210a6d2c1eb58e3f92a925
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1197"></a>Schwerwiegender Fehler C1197
"mscorlib.dll_1" kann nicht verwiesen werden, da das Programm bereits auf "mscorlib. dll_2" verweist.  
  
 Der Compiler ist eine Version der common Language Runtime zugeordnet.  Allerdings wurde versucht, eine Version einer common Language Runtime-Datei von einer früheren Version zu verweisen.  
  
 Um diesen Fehler zu beheben, müssen Sie nur verweisen Sie Dateien von der Version der common Language Runtime, die ausgeliefert wurden mit der Version von Visual C++, kompilieren Sie mit.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C1197 generiert:  
  
```  
// C1197.cpp  
// compile with: /clr /c  
// processor: x86  
#using "C:\Windows\Microsoft.NET\Framework\v1.1.4322\mscorlib.dll"   // C1197  
// try the following line instead  
// #using "mscorlib.dll"  
```
