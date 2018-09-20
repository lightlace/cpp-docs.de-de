---
title: _AddressOfReturnAddress | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _AddressOfReturnAddress_cpp
- _AddressOfReturnAddress
dev_langs:
- C++
helpviewer_keywords:
- _AddressOfReturnAddress intrinsic
- AddressOfReturnAddress intrinsic
ms.assetid: c7e10b8c-445e-4236-a602-e2d90200f70a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 694b9fead94bee55e1337df9511f59237ed88b57
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425807"
---
# <a name="addressofreturnaddress"></a>_AddressOfReturnAddress

**Microsoft-spezifisch**

Enthält die Adresse des Speicherorts im Arbeitsspeicher, der die Absenderadresse für die aktuelle Funktion enthält. Diese Adresse kann nicht auf andere Speicherorte (z. B. die Argumente der Funktion) verwendet werden.

## <a name="syntax"></a>Syntax

```
void * _AddressOfReturnAddress();
```

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_AddressOfReturnAddress`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Beim `_AddressOfReturnAddress` wird verwendet, in einem Programm mit kompiliert ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md), die Funktion, die `_AddressOfReturnAddress` Aufruf als eine native Funktion kompiliert wird. Wenn eine Funktion als kompiliert verwaltete Aufrufe an die Funktion mit `_AddressOfReturnAddress`, `_AddressOfReturnAddress` Verhalten sich ggf. nicht wie erwartet.

Diese Routine ist nur als systeminterne Funktion verfügbar.

## <a name="example"></a>Beispiel

```
// compiler_intrinsics_AddressOfReturnAddress.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

// This function will print three values:
//   (1) The address retrieved from _AddressOfReturnAdress
//   (2) The return address stored at the location returned in (1)
//   (3) The return address retrieved the _ReturnAddress* intrinsic
// Note that (2) and (3) should be the same address.
__declspec(noinline)
void func() {
   void* pvAddressOfReturnAddress = _AddressOfReturnAddress();
   printf_s("%p\n", pvAddressOfReturnAddress);
   printf_s("%p\n", *((void**) pvAddressOfReturnAddress));
   printf_s("%p\n", _ReturnAddress());
}

int main() {
   func();
}
```

```Output
0012FF78
00401058
00401058
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)