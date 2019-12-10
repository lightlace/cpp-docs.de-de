---
title: Compilerwarnung (Stufe 4) C4571
ms.date: 11/04/2016
f1_keywords:
- C4571
helpviewer_keywords:
- C4571
ms.assetid: 07aa17bd-b15c-4266-824c-57cc445e8edd
ms.openlocfilehash: 3a8f2093e90f8a681d171e19e2b8a066546f8684
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990657"
---
# <a name="compiler-warning-level-4-c4571"></a>Compilerwarnung (Stufe 4) C4571

Information: die catch (...)-Semantik wurde C++ seit Visual 7,1 geändert; strukturierte Ausnahmen (SEH) werden nicht mehr abgefangen.

C4571 wird für jeden catch-Block (...) bei der Kompilierung mit **/EHS**generiert.

Beim Kompilieren mit **/EHS**fängt ein catch-Block (...) keine strukturierte Ausnahme ab (z. b. Division durch 0 (null), z. b. NULL-Zeiger); ein catch-Block (...) fängt nur explizit ausgelöste C++ Ausnahmen ab.  Weitere Informationen finden Sie unter [Ausnahmebehandlung (Task Parallel Library)](../../cpp/exception-handling-in-visual-cpp.md).

Diese Warnung ist standardmäßig deaktiviert.  Aktivieren Sie diese Warnung, um sicherzustellen, dass Ihre Catch-Blöcke (...) bei der Kompilierung mit **/EHS** keine strukturierten Ausnahmen abfangen möchten.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Sie können C4571 auf eine der folgenden Arten auflösen:

- Kompilieren Sie mit **/EHa** , wenn Sie möchten, dass Ihre catch (...)-Blöcke strukturierte Ausnahmen abfangen.

- Aktivieren Sie C4571 nicht, wenn Sie nicht möchten, dass Ihre catch (...)-Blöcke strukturierte Ausnahmen abfangen, Sie aber weiterhin catch-Blöcke (...) verwenden möchten.  Sie können auch strukturierte Ausnahmen mithilfe der Schlüsselwörter für die strukturierte Ausnahmebehandlung ( **__try**, **__except**und **__finally**) auffangen.  Beachten Sie jedoch, dass kompilierte **/EHS** dededeerdektoren C++ nur aufgerufen werden, wenn eine Ausnahme ausgelöst wird, und nicht, wenn eine SEH-Ausnahme auftritt.

- Ersetzen Sie catch (...)-Block durch Catch- C++ Blöcke für bestimmte Ausnahmen, und fügen Sie optional eine strukturierte C++ Ausnahmebehandlung um die Ausnahmebehandlung ( **__try**, **__except**und **__finally**) hinzu.  Weitere Informationen finden Sie unter [strukturierte AusnahmeC++Behandlung (C/)](../../cpp/structured-exception-handling-c-cpp.md) .

Weitere Informationen finden Sie unter [/eh (Ausnahme Behandlungsmodell)](../../build/reference/eh-exception-handling-model.md) .

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4571 generiert.

```cpp
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
