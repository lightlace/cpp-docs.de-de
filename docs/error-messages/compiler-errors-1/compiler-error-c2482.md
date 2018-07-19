---
title: Compilerfehler C2482 | Microsoft Docs
ms.custom: ''
ms.date: 09/15/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2482
dev_langs:
- C++
helpviewer_keywords:
- C2482
ms.assetid: 98c87da2-625c-4cc2-9bf7-78d15921e779
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c3dd23069f389d0a02e10d26edb7ee4fd3c373cb
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
ms.locfileid: "34256005"
---
# <a name="compiler-error-c2482"></a>Compilerfehler C2482

>"*Bezeichner*": der dynamischen Initialisierung von "Thread"-Daten in verwalteten/WinRT-Code nicht zulässig

## <a name="remarks"></a>Hinweise

Beim verwalteten oder WinRT-code, Variablen, die deklariert, indem die [__declspec(thread)](../../cpp/thread.md) Speicher Modifizierer Klassenattribut oder [Thread_local](../../cpp/storage-classes-cpp.md#thread_local) -Speicherklassenspezifizierer kann nicht mit einem Ausdruck initialisiert werden die muss es sich um zur Laufzeit ausgewertet werden. Ein statischer Ausdruck ist erforderlich, um initialisieren `__declspec(thread)` oder `thread_local` Daten in diese Laufzeitumgebungen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C2482 generiert in verwaltet (**"/ CLR"**) und WinRT (**/Zw**) Code:

```cpp
// C2482.cpp
// For managed example, compile with: cl /EHsc /c /clr C2482.cpp
// For WinRT example, compile with: cl /EHsc /c /ZW C2482.cpp
#define Thread __declspec( thread )
Thread int tls_i1 = tls_i1;   // C2482

int j = j;   // OK in C++; C error
Thread int tls_i2 = sizeof( tls_i2 );   // Okay in C and C++
```

Um dieses Problem zu beheben, Initialisieren von lokalem Threadspeicher mithilfe einer Konstanten **Constexpr**, oder statischer Ausdruck. Initialisierungen threadspezifische separat ausführen.