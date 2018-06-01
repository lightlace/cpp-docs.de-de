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
ms.openlocfilehash: 1bdffdf3469cc3a0e5d41b0504b882513d44b63c
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34703986"
---
# <a name="linker-tools-warning-lnk4224"></a>Linkertoolwarnung LNK4224

> *Option* nicht mehr unterstützt; ignoriert

## <a name="remarks"></a>Hinweise

Eine ungültige, veraltete Linkeroption wurde angegeben und ignoriert.

LNK4224 kann beispielsweise auftreten, wenn eine comment-Direktive in angezeigt wird. Objekt Die comment-Direktive würde über hinzugefügt wurden die [Kommentar (C/C++)](../../preprocessor/comment-c-cpp.md) Pragmas, die als veraltet markierte Exestr verwenden. Verwenden von Dumpbin [/ALL](../../build/reference/all.md) So zeigen Sie die Linkerdirektiven in einer OBJ-Datei an.

Wenn möglich, ändern Sie die Quelle für die OBJ aus, und entfernen Sie das Pragma. Wenn Sie diese Warnung ignorieren, ist es möglich, dass der kompilierte .executable mit **/CLR: pure** nicht wie erwartet ausgeführt wird. Die **/CLR: pure** -Compileroption in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt wird.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird LNK4224 generiert.

```cpp
// LNK4224.cpp
// compile with: /c /Zi
// post-build command: link LNK4224.obj /debug /debugtype:map
int main () {
   return 0;
}
```