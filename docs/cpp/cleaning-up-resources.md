---
title: Bereinigen von Ressourcen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- termination handlers [C++], cleaning up resources
- exception handling [C++], cleaning up resources
- C++ exception handling, termination handlers
- resources [C++], cleaning up
- exception handling [C++], cleanup code
- try-catch keyword [C++], termination handlers
ms.assetid: 65753efe-6a27-4750-b90c-50635775c1b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: df75602dec8b27d12535e41b14fb2d7ca64061d1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076462"
---
# <a name="cleaning-up-resources"></a>Bereinigen von Ressourcen

Während der Ausführung des Beendigungshandlers wissen Sie möglicherweise nicht, welche Ressourcen tatsächlich zugeordnet wurden, bevor der Beendigungshandler aufgerufen wurde. Es ist möglich, die die **__try** Anweisungsblock wurde unterbrochen, bevor alle Ressourcen zugeordnet wurden, sodass nicht alle Ressourcen geöffnet wurden.

Vorsichtshalber sollten Sie daher überprüfen, welche Ressourcen tatsächlich geöffnet sind, bevor Sie die Bereinigung der Abbruchbehandlung fortsetzen. Dazu wird diese Vorgehensweise empfohlen:

1. Initialisieren Sie die Handles mit dem Wert NULL.

1. In der **__try** Anweisung blockiert, Ressourcen zuordnen. Beim Zuordnen der Ressourcen werden positive Werte für die Handles festgelegt.

1. In der **__finally** Anweisungsblock, release jede Ressource, deren entsprechender Handle oder Flagvariable ungleich NULL ist, oder nicht NULL.

## <a name="example"></a>Beispiel

Der folgende Code verwendet beispielsweise einen Beendigungshandler drei Dateien und einen Speicherblock, die in zugeordnet wurden schließen die **__try** Anweisungsblock. Bevor eine Ressource bereinigt wird, überprüft der Code zunächst, ob die Ressource zugeordnet wurde.

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

[Schreiben eines Beendigungshandlers](../cpp/writing-a-termination-handler.md)<br/>
[Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)