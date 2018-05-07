---
title: Linkertoolfehler Lnk2011 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2011
dev_langs:
- C++
helpviewer_keywords:
- LNK2011
ms.assetid: 04991ef5-49d5-46c7-8eee-a9d1d3fc541e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f60dce4cb260c670f5ee82aa88b9f106f3f14e2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk2011"></a>Linkertoolfehler LNK2011
vorkompilierte Objekt nicht verknüpft. Abbild kann möglicherweise nicht ausgeführt.  
  
 Bei Verwendung von vorkompilierten Headern erfordert LINK an, dass alle Objektdateien, die mit den vorkompilierten Header erstellt verknüpft werden muss. Wenn Sie eine Quelldatei, mit denen Sie einen vorkompilierten Header für die Verwendung mit anderen Quelldateien zu generieren verfügen, müssen Sie die Objektdatei zusammen mit den vorkompilierten Header erstellt jetzt einschließen.  
  
 Z. B. beim Kompilieren eine Datei namens STUB.cpp um einen vorkompilierten Header für die Verwendung mit anderen Quelldateien zu erstellen, müssen Sie eine Verknüpfung mit STUB.obj, oder Sie erhalten Sie diesen Fehler. In der folgenden Befehlszeilen wird eine Zeile verwendet, eine vorkompilierte Headerdatei COMMON.pch, zu erstellen, die in zwei und drei Zeilen mit PROG1.cpp und PROG2.cpp verwendet wird. Die Datei STUB.cpp nur enthält `#include` Zeilen (dem `#include` Zeilen wie PROG1.cpp und PROG2.cpp) und dient nur zum Generieren von vorkompilierten Headern. In der letzten Zeile muss STUB.obj verknüpft werden, um LNK2011 zu vermeiden.  
  
```  
cl /c /Yccommon.h stub.cpp  
cl /c /Yucommon.h prog1.cpp  
cl /c /Yucommon.h prog2.cpp  
link /out:prog.exe stub.obj prog1.obj prog2.obj  
```