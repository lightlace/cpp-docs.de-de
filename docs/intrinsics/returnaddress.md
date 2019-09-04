---
title: _ReturnAddress
ms.date: 09/02/2019
f1_keywords:
- _ReturnAddress
helpviewer_keywords:
- _ReturnAddress intrinsic
- ReturnAddress intrinsic
ms.assetid: 7f4a5811-35e6-4f64-ba7c-21203380eeda
ms.openlocfilehash: 2a830ff1e8a2c9551dec52cf10a3d5cf126bde3b
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218060"
---
# <a name="_returnaddress"></a>_ReturnAddress

**Microsoft-spezifisch**

Die `_ReturnAddress` systeminterne Funktion stellt die Adresse der Anweisung in der aufrufenden Funktion bereit, die ausgeführt wird, nachdem die Steuerung an den Aufrufer zurückgegeben wurde.

Erstellen Sie das folgende Programm, und durchlaufen Sie es im Debugger. Wenn Sie das Programm schrittweise durchlaufen, notieren Sie sich die Adresse `_ReturnAddress`, die von zurückgegeben wird. Öffnen Sie dann unmittelbar nach der Rückgabe der Funktion `_ReturnAddress` , in der verwendet wurde [, die Vorgehensweise: Verwenden Sie das Fenster](/visualstudio/debugger/how-to-use-the-disassembly-window) Disassembly, und beachten Sie, dass die Adresse der nächsten Anweisung, die ausgeführt werden soll, mit der von `_ReturnAddress`zurückgegebenen Adresse übereinstimmt.

Optimierungen wie Inlining können sich auf die Rückgabeadresse auswirken. Wenn beispielsweise das unten aufgeführte Beispielprogramm mit [/ob1](../build/reference/ob-inline-function-expansion.md)kompiliert wird `inline_func` , wird in `main`die aufrufende Funktion () eingebunden. Daher wird bei den Aufrufen `_ReturnAddress` von `inline_func` von `main` und jeweils der gleiche Wert erzeugt.

Wenn `_ReturnAddress` in einem Programm verwendet wird, das mit [/CLR](../build/reference/clr-common-language-runtime-compilation.md)kompiliert wurde, wird `_ReturnAddress` die Funktion, die den-aufrufsvorgang enthält, als native Funktion kompiliert. Wenn eine Funktion, die als verwaltete Aufrufe der Funktion, `_ReturnAddress`die `_ReturnAddress` enthält, kompiliert wird, verhält sich möglicherweise nicht wie erwartet.

## <a name="requirements"></a>Anforderungen

**Header Datei** \<intrin. h->

## <a name="example"></a>Beispiel

```cpp
// compiler_intrinsics__ReturnAddress.cpp
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_ReturnAddress)

__declspec(noinline)
void noinline_func(void)
{
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());
}

__forceinline
void inline_func(void)
{
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());
}

int main(void)
{
   noinline_func();
   inline_func();
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());

   return 0;
}
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_AddressOfReturnAddress](../intrinsics/addressofreturnaddress.md)\
[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[Schlüsselwörter](../cpp/keywords-cpp.md)
