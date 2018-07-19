---
title: Schwerwiegender Fehler C1197 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1197
dev_langs:
- C++
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dacd459729161cf635287697a4a6d35c15eab3e4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33227275"
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