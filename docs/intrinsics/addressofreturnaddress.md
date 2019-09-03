---
title: _AddressOfReturnAddress
ms.date: 09/02/2019
f1_keywords:
- _AddressOfReturnAddress_cpp
- _AddressOfReturnAddress
helpviewer_keywords:
- _AddressOfReturnAddress intrinsic
- AddressOfReturnAddress intrinsic
ms.assetid: c7e10b8c-445e-4236-a602-e2d90200f70a
ms.openlocfilehash: d705029c30fdbc117c4c6e96923691e43e072e23
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221072"
---
# <a name="_addressofreturnaddress"></a>_AddressOfReturnAddress

**Microsoft-spezifisch**

Gibt die Adresse des Speicher Orts an, der die Rückgabeadresse der aktuellen Funktion enthält. Diese Adresse darf nicht für den Zugriff auf andere Speicherorte (z. b. die Argumente der Funktion) verwendet werden.

## <a name="syntax"></a>Syntax

```C
void * _AddressOfReturnAddress();
```

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_AddressOfReturnAddress`|x86, x64, ARM, ARM64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Wenn `_AddressOfReturnAddress` in einem Programm verwendet wird, das mit [/CLR](../build/reference/clr-common-language-runtime-compilation.md)kompiliert wurde, wird `_AddressOfReturnAddress` die Funktion, die den-Befehl enthält, als native Funktion kompiliert. Wenn eine Funktion, die als verwaltete Aufrufe der Funktion, `_AddressOfReturnAddress`die `_AddressOfReturnAddress` enthält, kompiliert wird, verhält sich möglicherweise nicht wie erwartet.

Diese Routine ist nur als systeminterne Funktion verfügbar.

## <a name="example"></a>Beispiel

```cpp
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

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[Schlüsselwörter](../cpp/keywords-cpp.md)
