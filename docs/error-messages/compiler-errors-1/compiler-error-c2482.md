---
title: Compilerfehler C2482
ms.date: 09/15/2017
f1_keywords:
- C2482
helpviewer_keywords:
- C2482
ms.assetid: 98c87da2-625c-4cc2-9bf7-78d15921e779
ms.openlocfilehash: 481920fa2d8c32bc872e7b8805188cc674e6fe28
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375053"
---
# <a name="compiler-error-c2482"></a>Compilerfehler C2482

>"*Bezeichner*": dynamische Initialisierung von "Thread" Daten, die in verwalteten/WinRT-Code nicht zulässig

## <a name="remarks"></a>Hinweise

Beim verwalteten oder WinRT-code, Variablen, die mithilfe der [__declspec(thread)](../../cpp/thread.md) Storage-Class-Modifizierer-Attribut oder das [Thread_local](../../cpp/storage-classes-cpp.md#thread_local) -Speicherklassenspezifizierer kann nicht mit einem Ausdruck initialisiert werden Auswertung zur Laufzeit erforderlich. Ein statischer Ausdruck ist erforderlich, um das Initialisieren `__declspec(thread)` oder `thread_local` Daten in diesen Umgebungen von Common Language Runtime.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C2482 generiert in verwaltet (**"/ CLR"**) und in WinRT (**/Zw**) Code:

```cpp
// C2482.cpp
// For managed example, compile with: cl /EHsc /c /clr C2482.cpp
// For WinRT example, compile with: cl /EHsc /c /ZW C2482.cpp
#define Thread __declspec( thread )
Thread int tls_i1 = tls_i1;   // C2482

int j = j;   // OK in C++; C error
Thread int tls_i2 = sizeof( tls_i2 );   // Okay in C and C++
```

Um dieses Problem beheben, Initialisieren von lokalen Thread-Speicher mithilfe einer Konstanten, **"constexpr"**, oder ein statischer Ausdruck. Initialisierungen threadspezifische separat ausführen.