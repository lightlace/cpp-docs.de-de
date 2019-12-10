---
title: Compilerwarnung (Stufe 4) C4820
ms.date: 11/04/2016
f1_keywords:
- C4820
helpviewer_keywords:
- C4820
ms.assetid: 17aa29f4-c287-49b8-bc43-8ed82ffed5ea
ms.openlocfilehash: ac97a943e6a8178e930d93a097071b0e3da09773
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74989066"
---
# <a name="compiler-warning-level-4-c4820"></a>Compilerwarnung (Stufe 4) C4820

'Bytes' Bytes Abstand nach dem Konstrukt 'member_name'

Der Typ und die Reihenfolge der Elemente bewirkt, dass der Compiler Auffüll Zeichen am Ende einer Struktur hinzugefügt hat. Weitere Informationen zum Auffüllen in einer Struktur finden Sie unter [Ausrichten](../../cpp/align-cpp.md) .

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Im folgenden Beispiel wird C4820 generiert:

```cpp
// C4820.cpp
// compile with: /W4 /c
#pragma warning(default : 4820)

// Delete the following 4 lines to resolve.
__declspec(align(2)) struct MyStruct {
   char a;
   int i;   // C4820
};

// OK
#pragma pack(1)
__declspec(align(1)) struct MyStruct2 {
   char a;
   int i;
};
```
