---
title: Kombination von C (strukturierte) und C++-Ausnahmen
ms.date: 08/14/2018
helpviewer_keywords:
- exceptions [C++], mixed C and C++
- C++ exception handling, mixed-language
- structured exception handling [C++], mixed C and C++
- catch keyword [C++], mixed
- try-catch keyword [C++], mixed-language
ms.assetid: a149154e-36dd-4d1a-980b-efde2a563a56
ms.openlocfilehash: 94d6dc249cb130aaf09d3202b9e8f437d00a9597
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345956"
---
# <a name="mixing-c-structured-and-c-exceptions"></a>Kombination von C (strukturierte) und C++-Ausnahmen

Wenn Sie portablen Code schreiben möchten, nicht die Verwendung der strukturierten Ausnahmebehandlung (SEH) in einem C++-Programm empfohlen. Allerdings unter Umständen möchten Sie Kompilieren mit der [/EHa](../build/reference/eh-exception-handling-model.md) und strukturierte Ausnahmen und C++-Quellcode kombinieren und benötigen daher einige Funktionen zur Behandlung beider Arten von Ausnahmen. Da ein strukturierter Ausnahmehandler kein Konzept für die Objekte oder von typisierten Ausnahmen verfügt, kann es von C++-Code ausgelöste Ausnahmen nicht behandeln. Jedoch C++ **catch** Handler können strukturierte Ausnahmen behandeln. C++Syntax für die Ausnahmebehandlung (**versuchen**, **auslösen**, **catch**) wird nicht akzeptiert, durch den C-Compiler, aber strukturierte ausnahmebehandlungssyntax (**__try**, **__except**, **__finally**) wird von unterstützt die C++ Compiler.

Finden Sie unter [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) Informationen zur Behandlung strukturierte Ausnahmen als C++ Ausnahmen.

Wenn Sie strukturierte kombinieren und C++-Ausnahmen, die dieser potenziellen Probleme berücksichtigen:

- C++-Ausnahmen und strukturierte Ausnahmen können nicht in derselben Funktion kombiniert werden.

- Beendigungshandler (**__finally** Blöcke) werden immer ausgeführt, sogar während des Entladens, nachdem eine Ausnahme ausgelöst wird.

- C++-Ausnahmebehandlung kann abfangen und Beibehalten von entladungssemantik in allen Modulen mit kompiliert die [/EH](../build/reference/eh-exception-handling-model.md) Compileroptionen, die Entladesemantik für welche aktivieren.

- Es kann Situationen geben, in denen Destruktorfunktionen nicht für alle Objekte aufgerufen werden. Z. B. wenn eine strukturierte Ausnahme tritt auf, bei dem Versuch, eine Funktion über einen nicht initialisierten Funktionszeiger aufrufen und diese Funktion Objekte als Parameter nutzt, die vor dem Aufruf erstellt wurden, die Destruktoren dieser Objekte nicht heißen während der stapelentladung.

## <a name="next-steps"></a>Nächste Schritte

- [Verwenden von Setjmp oder Longjmp in C++-Programmen](../cpp/using-setjmp-longjmp.md)

  Finden Sie weitere Informationen zur Verwendung von `setjmp` und `longjmp` in C++-Programmen.

- [Behandeln strukturierter Ausnahmen in C++](../cpp/exception-handling-differences.md)

  Finden Sie Beispiele für die Möglichkeiten zum Ausnahmen behandeln, die strukturierte C++ verwendet werden können.

## <a name="see-also"></a>Siehe auch

[C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)
