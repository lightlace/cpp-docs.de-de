---
title: Linkertoolfehler Lnk2011 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2011
dev_langs: C++
helpviewer_keywords: LNK2011
ms.assetid: 04991ef5-49d5-46c7-8eee-a9d1d3fc541e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9811bdb905df61bb77ea4af6bc4ced7c4ba42106
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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