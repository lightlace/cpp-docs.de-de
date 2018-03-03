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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1658e55a9298df703051b856bb9b10dd02d8cc68
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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