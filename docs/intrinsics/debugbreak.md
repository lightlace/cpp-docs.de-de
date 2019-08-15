---
title: __debugbreak
ms.date: 11/04/2016
f1_keywords:
- __debugbreak_cpp
- __debugbreak
helpviewer_keywords:
- breakpoints, __debugbreak intrinsic
- __debugbreak intrinsic
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
ms.openlocfilehash: ed75b94e8bf0aca9369c56f23e8ff00ea6953642
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509499"
---
# <a name="__debugbreak"></a>__debugbreak

**Microsoft-spezifisch**

Bewirkt, dass ein Haltepunkt im Code festgelegt wird, an dem der Benutzer zum Ausführen des Debuggers aufgefordert wird.

## <a name="syntax"></a>Syntax

```
void __debugbreak();
```

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|Header|
|---------------|------------------|------------|
|`__debugbreak`|x86, x64, ARM, ARM64|\<intrin.h>|

## <a name="remarks"></a>Hinweise

Der `__debugbreak` systeminterne Compiler ist, ähnlich wie bei der [Debugger](/windows/win32/api/debugapi/nf-debugapi-debugbreak), eine Portable Win32-Methode, um einen Breakpoint auszulösen.

> [!NOTE]
>  Beim Kompilieren mit **/CLR**wird eine Funktion, `__debugbreak` die enthält, in MSIL kompiliert. `asm int 3` bewirkt, dass eine Funktion in systemeigenem Code kompiliert wird. Weitere Informationen finden Sie unter [__asm](../assembler/inline/asm.md).

Beispiel:

```
main() {
   __debugbreak();
}
```

ist vergleichbar mit:

```
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

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)
