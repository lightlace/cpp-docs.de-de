---
title: Compilerwarnung (Stufe 3) C4792
ms.date: 11/04/2016
f1_keywords:
- C4792
helpviewer_keywords:
- C4792
ms.assetid: c047ce69-a622-44e1-9425-d41aa9261c61
ms.openlocfilehash: f0efed41fad2648d7e681fa4e5575e7f36fb6aeb
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991674"
---
# <a name="compiler-warning-level-3-c4792"></a>Compilerwarnung (Stufe 3) C4792

Die Funktion 'Funktion' wurde unter Verwendung von „sysimport“ und durch Verweis von systemeigenem Code deklariert. Eine Importbibliothek ist zum Verknüpfen erforderlich.

Eine mit „DllImport“ importierte systemeigene Funktion wurde von einer nicht verwalteten Funktion aufgerufen. Daher müssen Sie für die DLL eine Verknüpfung mit der Importbibliothek herstellen.

Diese Warnung kann nicht im Code oder durch Ändern der Kompilierungsweise aufgelöst werden. Verwenden Sie das [warning](../../preprocessor/warning.md) -Pragma, um diese Warnung zu deaktivieren.

Im folgenden Beispiel wird C4792 generiert.

```cpp
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
