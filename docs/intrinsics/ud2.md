---
title: __ud2
ms.date: 09/02/2019
f1_keywords:
- __ud2
helpviewer_keywords:
- UD2 instruction
- __ud2 intrinsic
ms.assetid: 0831cd5a-8b65-402e-bb57-11e1d5d7ffd2
ms.openlocfilehash: b5aa20804099af4d75dcc62a5e62ccc0d4a09566
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219756"
---
# <a name="__ud2"></a>__ud2

**Microsoft-spezifisch**

Generiert eine nicht definierte Anweisung.

## <a name="syntax"></a>Syntax

```C
void __ud2();
```

## <a name="remarks"></a>Hinweise

Der Prozessor löst eine ungültige Opcode-Ausnahme aus, wenn Sie eine nicht definierte Anweisung ausführen.

Die `__ud2` -Funktion entspricht der `UD2` -Computer Anweisung und ist nur im Kernel Modus verfügbar. Weitere Informationen finden Sie im Dokument "Intel Architecture Software Developer es Manual, Volume 2: Anweisungs Satz Verweis "auf der Website der [Intel Corporation](https://software.intel.com/articles/intel-sdm) .

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__ud2`|x86, x64|

**Header Datei** \<intrin. h->

**Ende Microsoft-spezifisch**

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine nicht definierte-Anweisung ausgeführt, die eine Ausnahme auslöst. Der Ausnahmehandler ändert dann den Rückgabecode von 0 (null) in einen Wert.

```cpp
// __ud2_intrinsic.cpp
#include <stdio.h>
#include <intrin.h>
#include <excpt.h>
// compile with /EHa

int main() {

// Initialize the return code to 0.
int ret = 0;

// Attempt to execute an undefined instruction.
  printf("Before __ud2(). Return code = %d.\n", ret);
  __try {
  __ud2();
  }

// Catch any exceptions and set the return code to 1.
  __except(EXCEPTION_EXECUTE_HANDLER){
  printf("  In the exception handler.\n");
  ret = 1;
  }

// Report the value of the return code.
  printf("After __ud2().  Return code = %d.\n", ret);
  return ret;
}
```

```Output
Before __ud2(). Return code = 0.
  In the exception handler.
After __ud2().  Return code = 1.
```

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
