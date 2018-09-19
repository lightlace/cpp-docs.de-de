---
title: Compilerwarnung (Stufe 4) C4571 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4571
dev_langs:
- C++
helpviewer_keywords:
- C4571
ms.assetid: 07aa17bd-b15c-4266-824c-57cc445e8edd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1291466ffd9071929194ffbe7795addfec62eb27
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088318"
---
# <a name="compiler-warning-level-4-c4571"></a>Compilerwarnung (Stufe 4) C4571

Information: catch(...)-Semantik Visual C++ 7.1 geändert; strukturierte Ausnahmen (SEH) werden nicht mehr abgefangen.

C4571 wird für jeden catch(...) beim Kompilieren mit **/EHs**.

Beim Kompilieren mit **/EHs**, ein wird kein catch(...) eine strukturierte Ausnahme (Division durch 0 (null), null-Zeiger ist z. B.), einem catch(...) Block wird nur Catch explizit ausgelöste, C++-Ausnahmen.  Weitere Informationen finden Sie unter [Ausnahmebehandlung (Task Parallel Library)](../../cpp/exception-handling-in-visual-cpp.md).

Diese Warnung ist standardmäßig deaktiviert.  Aktivieren Sie diese Warnung auf, um sicherzustellen, dass beim Kompilieren mit **/EHs** Ihrer (...)-Catch-Blöcke nicht strukturierte Ausnahmen abfangen möchten.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Sie können in einem der folgenden Arten C4571 behoben haben,

- Kompilieren Sie mit **/EHa** Falls Sie weiterhin Ihre catch(...)-Blöcke zum Abfangen von strukturierter Ausnahmen benötigen.

- Aktivieren Sie C4571 nicht, wenn Sie nicht möchten, dass Ihre catch(...)-Blöcke zum Abfangen von strukturierter Ausnahmen, aber dennoch catch(...)-Blöcke verwenden möchten.  Sie können weiterhin abfangen, strukturierte Ausnahmen, die die strukturierte Ausnahmebehandlung Schlüsselwörter (**__try**, **__except**, und **__finally**).  Beachten Sie jedoch, dass kompiliert **/EHs** Destruktoren werden nur aufgerufen werden, wenn eine C++-Ausnahme ausgelöst wird, nicht verwendet werden, wenn SEH-Ausnahmen,.

- Ersetzen Sie catch(...) Block mit Catch-Blöcke für bestimmte C++-Ausnahmen aus, und fügen Sie optional auf die die C++-Ausnahmebehandlung die strukturierte Ausnahmebehandlung hinzu (**__try**, **__except**, und **_ __identifier**).  Finden Sie unter [Structured Exception Handling (C/C++)](../../cpp/structured-exception-handling-c-cpp.md) für Weitere Informationen.

Finden Sie unter [/EH (Ausnahmebehandlungsmodell)](../../build/reference/eh-exception-handling-model.md) für Weitere Informationen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4571 generiert.

```
// C4571.cpp
// compile with: /EHs /W4 /c
#pragma warning(default : 4571)
int main() {
   try {
      int i = 0, j = 1;
      j /= i;   // this will throw a SE (divide by zero)
   }
   catch(...) {}   // C4571 warning
}
```