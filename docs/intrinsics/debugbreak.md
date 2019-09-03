---
title: __debugbreak
ms.date: 09/02/2019
f1_keywords:
- __debugbreak_cpp
- __debugbreak
helpviewer_keywords:
- breakpoints, __debugbreak intrinsic
- __debugbreak intrinsic
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
ms.openlocfilehash: e4cf2c85818a878417c560ddb5a80f8690e60a93
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217921"
---
# <a name="__debugbreak"></a>__debugbreak

**Microsoft-spezifisch**

Bewirkt, dass ein Haltepunkt im Code festgelegt wird, an dem der Benutzer zum Ausführen des Debuggers aufgefordert wird.

## <a name="syntax"></a>Syntax

```C
void __debugbreak();
```

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|Header|
|---------------|------------------|------------|
|`__debugbreak`|x86, x64, ARM, ARM64|\<intrin.h>|

## <a name="remarks"></a>Hinweise

Der `__debugbreak` systeminterne Compiler ist, ähnlich wie bei der [Debugger](/windows/win32/api/debugapi/nf-debugapi-debugbreak), eine Portable Win32-Methode, um einen Breakpoint auszulösen.

> [!NOTE]
> Beim Kompilieren mit **/CLR**wird eine Funktion, `__debugbreak` die enthält, in MSIL kompiliert. `asm int 3` bewirkt, dass eine Funktion in systemeigenem Code kompiliert wird. Weitere Informationen finden Sie unter [__asm](../assembler/inline/asm.md).

Beispiel:

```C
main() {
   __debugbreak();
}
```

ist vergleichbar mit:

```C
main() {
   __asm {
      int 3
   }
}
```

auf einem x86-Computer.

Auf ARM64 wird der `__debugbreak` systeminterne in die Anweisung `brk #0xF000`kompiliert.

Diese Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[Schlüsselwörter](../cpp/keywords-cpp.md)
