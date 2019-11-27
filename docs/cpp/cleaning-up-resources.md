---
title: Bereinigen von Ressourcen
ms.date: 11/04/2016
helpviewer_keywords:
- termination handlers [C++], cleaning up resources
- exception handling [C++], cleaning up resources
- C++ exception handling, termination handlers
- resources [C++], cleaning up
- exception handling [C++], cleanup code
- try-catch keyword [C++], termination handlers
ms.assetid: 65753efe-6a27-4750-b90c-50635775c1b6
ms.openlocfilehash: 225c3ccaf3342f11ad4eb6d6575ad3ac542acfd2
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246636"
---
# <a name="cleaning-up-resources"></a>Bereinigen von Ressourcen

Während der Ausführung des Beendigungshandlers wissen Sie möglicherweise nicht, welche Ressourcen tatsächlich zugeordnet wurden, bevor der Beendigungshandler aufgerufen wurde. Es ist möglich, dass der **__try** -Anweisungsblock unterbrochen wurde, bevor alle Ressourcen zugewiesen wurden, sodass nicht alle Ressourcen geöffnet wurden.

Vorsichtshalber sollten Sie daher überprüfen, welche Ressourcen tatsächlich geöffnet sind, bevor Sie die Bereinigung der Abbruchbehandlung fortsetzen. Dazu wird diese Vorgehensweise empfohlen:

1. Initialisieren Sie die Handles mit dem Wert NULL.

1. Weisen Sie im **__try** -Anweisungsblock Ressourcen zu. Beim Zuordnen der Ressourcen werden positive Werte für die Handles festgelegt.

1. Geben Sie im **__finally** -Anweisungsblock jede Ressource frei, deren zugehörige handle-oder Flag-Variable ungleich NULL oder nicht NULL ist.

## <a name="example"></a>Beispiel

Der folgende Code verwendet beispielsweise einen Beendigungs Handler, um drei Dateien und einen Speicherblock zu schließen, die im **__try** Anweisungsblock zugeordnet wurden. Bevor eine Ressource bereinigt wird, überprüft der Code zunächst, ob die Ressource zugeordnet wurde.

```cpp
// exceptions_Cleaning_up_Resources.cpp
#include <stdlib.h>
#include <malloc.h>
#include <stdio.h>
#include <windows.h>

void fileOps() {
   FILE  *fp1 = NULL,
         *fp2 = NULL,
         *fp3 = NULL;
   LPVOID lpvoid = NULL;
   errno_t err;

   __try {
      lpvoid = malloc( BUFSIZ );

      err = fopen_s(&fp1, "ADDRESS.DAT", "w+" );
      err = fopen_s(&fp2, "NAMES.DAT", "w+" );
      err = fopen_s(&fp3, "CARS.DAT", "w+" );
   }
   __finally {
      if ( fp1 )
         fclose( fp1 );
      if ( fp2 )
         fclose( fp2 );
      if ( fp3 )
         fclose( fp3 );
      if ( lpvoid )
         free( lpvoid );
   }
}

int main() {
   fileOps();
}
```

## <a name="see-also"></a>Siehe auch

[Schreiben eines Beendigungs Handlers](../cpp/writing-a-termination-handler.md)<br/>
[Structured Exception Handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)