---
title: Linkertoolwarnung LNK4224
ms.date: 11/04/2016
f1_keywords:
- LNK4224
helpviewer_keywords:
- LNK4224
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
ms.openlocfilehash: eb0a019cc80e5218a52697b8bcd5e91b811d04d3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50465324"
---
# <a name="linker-tools-warning-lnk4224"></a>Linkertoolwarnung LNK4224

> *Option* ist nicht mehr unterstütz; ignoriert

## <a name="remarks"></a>Hinweise

Eine ungültige, veraltete-Linkeroption wurde angegeben und wird ignoriert.

LNK4224 kann beispielsweise auftreten, wenn in eine/COMMENT-Anweisung angezeigt wird. obj. Die Direktive/Comment würde wurden hinzugefügt, über die [Kommentar (C/C++)](../../preprocessor/comment-c-cpp.md) Pragmas, die als veraltet markierte Exestr verwenden. Verwenden von Dumpbin [/ALL](../../build/reference/all.md) So zeigen Sie die Linker-Anweisungen in einer OBJ-Datei an.

Wenn möglich, ändern Sie die Quelle für die .obj, und entfernen Sie das Pragma. Wenn Sie diese Warnung ignorieren, ist es möglich, dass die kompilierte .executable mit **/CLR: pure** nicht wie erwartet ausgeführt wird. Die **/CLR: pure** Compileroption ist in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die LNK4224 generiert.

```cpp
// LNK4224.cpp
// compile with: /c /Zi
// post-build command: link LNK4224.obj /debug /debugtype:map
int main () {
   return 0;
}
```