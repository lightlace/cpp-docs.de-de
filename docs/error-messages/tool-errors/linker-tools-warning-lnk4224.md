---
title: Linkertoolwarnung Lnk4224 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4224
dev_langs:
- C++
helpviewer_keywords:
- LNK4224
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 96399e0c66eb3cb719073b2318513cd680723d97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4224"></a>Linkertoolwarnung LNK4224
Option ist nicht mehr unterstützt. ignoriert  
  
 Eine ungültige, veraltete Linkeroption wurde angegeben und ignoriert.  
  
 LNK4224 kann beispielsweise auftreten, wenn eine comment-Direktive in angezeigt wird. Objekt Die comment-Direktive würde über hinzugefügt wurden die [Kommentar (C/C++)](../../preprocessor/comment-c-cpp.md) Pragmas, die als veraltet markierte Exestr verwenden. Verwenden von Dumpbin [/ALL](../../build/reference/all.md) So zeigen Sie die Linkerdirektiven in einer OBJ-Datei an.  
  
 Wenn möglich, ändern Sie die Quelle für die OBJ aus, und entfernen Sie das Pragma. Wenn Sie diese Warnung ignorieren, ist es möglich, dass der kompilierte .executable mit **/CLR: pure** nicht wie erwartet ausgeführt wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird LNK4224 generiert.  
  
```  
// LNK4224.cpp  
// compile with: /c /Zi  
// post-build command: link LNK4224.obj /debug /debugtype:map  
int main () {  
   return 0;  
}  
```