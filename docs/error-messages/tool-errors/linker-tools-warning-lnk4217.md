---
title: Linkertoolwarnung Lnk4217 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4217
dev_langs:
- C++
helpviewer_keywords:
- LNK4217
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 625f3a1b8a67f198b1cb4ca37bd1350229ec20db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300575"
---
# <a name="linker-tools-warning-lnk4217"></a>Linkertoolwarnung LNK4217
Lokal definiertes Symbol 'Symbol' in Funktion 'Funktion' importiert  
  
 [von "__declspec(dllimport)" "](../../cpp/dllexport-dllimport.md) wurde für ein Symbol angegeben, obwohl das Symbol lokal definiert wurde. Entfernen Sie die `__declspec` Modifizierer, um diese Warnung zu beheben.  
  
 `symbol` ist der Symbolname, der innerhalb des Bilds definiert ist. `function` ist die Funktion, die das Symbol importiert wird.  
  
 Diese Warnung wird nicht angezeigt, wenn Sie Kompilieren mit der Option ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 LNK4217 kann auch auftreten, wenn Sie versuchen, zwei Module miteinander zu verknüpfen, wenn stattdessen das zweite Modul mit der Importbibliothek der ersten Modul kompiliert werden soll.  
  
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
  
 Bei dem Versuch, verknüpfen Sie diese beiden Module LNK4217 deutlichen, kompilieren Sie das zweite Beispiel mit der Importbibliothek her, der im ersten Beispiel aufgelöst.