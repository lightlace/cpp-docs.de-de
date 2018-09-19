---
title: Compilerwarnung (Stufe 3) C4792 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4792
dev_langs:
- C++
helpviewer_keywords:
- C4792
ms.assetid: c047ce69-a622-44e1-9425-d41aa9261c61
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4afb08cbe3203ff462f59fec4c1e712aa024c081
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136061"
---
# <a name="compiler-warning-level-3-c4792"></a>Compilerwarnung (Stufe 3) C4792

Die Funktion 'Funktion' wurde unter Verwendung von „sysimport“ und durch Verweis von systemeigenem Code deklariert. Eine Importbibliothek ist zum Verknüpfen erforderlich.

Eine mit „DllImport“ importierte systemeigene Funktion wurde von einer nicht verwalteten Funktion aufgerufen. Daher müssen Sie für die DLL eine Verknüpfung mit der Importbibliothek herstellen.

Diese Warnung kann nicht im Code oder durch Ändern der Kompilierungsweise aufgelöst werden. Verwenden Sie das [warning](../../preprocessor/warning.md) -Pragma, um diese Warnung zu deaktivieren.

Im folgenden Beispiel wird C4792 generiert.

```
// C4792.cpp
// compile with: /clr /W3
// C4792 expected
using namespace System::Runtime::InteropServices;
[DllImport("msvcrt")]
extern "C" int __cdecl puts(const char *);
int main() {}

// Uncomment the following line to resolve.
// #pragma warning(disable : 4792)
#pragma unmanaged
void func(void){
   puts("test");
}
```