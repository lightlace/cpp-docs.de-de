---
title: 'Vorgehensweise: Anheften von Zeigern und Arrays'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- pointers, pinning
- arrays [C++], pinning
ms.assetid: ee783260-e676-46b8-a38e-11a06f1d57b0
ms.openlocfilehash: ae8c1da79f41cf9209f2765ce5aa2f7ca3d34aea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "65515685"
---
# <a name="how-to-pin-pointers-and-arrays"></a>Vorgehensweise: Anheften von Zeigern und Arrays

Das Anheften eines untergeordneten Objekts, das in einem verwalteten Objekt definiert ist, hat den gleichen Effekt wie das Anheften des gesamten Objekts.  Wenn z.B. ein Element eines Arrays angeheftet wird, wird auch das gesamte Array angeheftet. Es gibt keine Erweiterungen für die Sprache zum Deklarieren eines angehefteten Arrays. Um ein Array anzuheften, deklarieren Sie einen festen Zeiger für dessen Elementtyp, und heften Sie eines seiner Elemente an.

## <a name="example"></a>Beispiel

### <a name="code"></a>Code

```cpp
// pin_ptr_array.cpp
// compile with: /clr
#include <stdio.h>
using namespace System;

int main() {
   array<Byte>^ arr = gcnew array<Byte>(4);
   arr[0] = 'C';
   arr[1] = '+';
   arr[2] = '+';
   arr[3] = '\0';
   pin_ptr<Byte> p = &arr[1];   // entire array is now pinned
   unsigned char * cp = p;

   printf_s("%s\n", cp); // bytes pointed at by cp
                         // will not move during call
}
```

```Output
++
```

## <a name="see-also"></a>Siehe auch

[pin_ptr (C++/CLI)](pin-ptr-cpp-cli.md)