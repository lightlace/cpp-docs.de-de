---
title: Linkertoolwarnung Lnk4224 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4224
dev_langs:
- C++
helpviewer_keywords:
- LNK4224
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a051e341a22871b4229617b3958cb68dedc2921
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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