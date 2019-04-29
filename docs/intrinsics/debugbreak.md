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
ms.openlocfilehash: b52c34014402a235e03c45f82dcd1e5c542e4919
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349042"
---
# <a name="debugbreak"></a>__debugbreak

**Microsoft-spezifisch**

Bewirkt, dass ein Haltepunkt im Code festgelegt wird, an dem der Benutzer zum Ausführen des Debuggers aufgefordert wird.

## <a name="syntax"></a>Syntax

```
void __debugbreak();
```

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|Header|
|---------------|------------------|------------|
|`__debugbreak`|x86, ARM, x64|\<intrin.h>|

## <a name="remarks"></a>Hinweise

Die `__debugbreak` systeminterne Compilerfunktion ähnelt ["DebugBreak"](https://msdn.microsoft.com/library/windows/desktop/ms679297.aspx), ist eine portable Win32-Methode, die einen Haltepunkt bewirkt.

> [!NOTE]
>  Beim Kompilieren mit **"/ CLR"**, eine Funktion, `__debugbreak` in MSIL kompiliert wird. `asm int 3` bewirkt, dass eine Funktion in systemeigenem Code kompiliert wird. Weitere Informationen finden Sie unter [__asm](../assembler/inline/asm.md).

Zum Beispiel:

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

Diese Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)