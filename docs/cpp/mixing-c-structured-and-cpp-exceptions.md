---
title: Mischen von C (strukturiert) C++ und Ausnahmen
ms.date: 08/14/2018
helpviewer_keywords:
- exceptions [C++], mixed C and C++
- C++ exception handling, mixed-language
- structured exception handling [C++], mixed C and C++
- catch keyword [C++], mixed
- try-catch keyword [C++], mixed-language
ms.assetid: a149154e-36dd-4d1a-980b-efde2a563a56
ms.openlocfilehash: e49731f1c81057002eaae2bef16cda4a5cf86f8d
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246459"
---
# <a name="mixing-c-structured-and-c-exceptions"></a>Mischen von C (strukturiert) C++ und Ausnahmen

Wenn Sie portablen Code schreiben möchten, wird die Verwendung der strukturierten Ausnahmebehandlung (SEH) in C++ einem Programm nicht empfohlen. Möglicherweise möchten Sie jedoch mit [/EHa](../build/reference/eh-exception-handling-model.md) kompilieren und strukturierte Ausnahmen und C++ Quellcode mischen und einige Möglichkeiten für die Behandlung beider Arten von Ausnahmen benötigen. Da ein strukturierter Ausnahmehandler kein Konzept von Objekten oder typisierten Ausnahmen hat, kann er keine Ausnahmen verarbeiten C++ , die von Code ausgelöst werden. C++ Allerdings können **catch** -Handler strukturierte Ausnahmen verarbeiten. C++die Syntax für die Ausnahmebehandlung (**try**, **throw**, **catch**) wird vom C-Compiler nicht akzeptiert, aber die Syntax für die C++ strukturierte Ausnahmebehandlung ( **__try**, **__except** **__finally**) wird vom Compiler unterstützt.

Informationen zur Behandlung strukturierter Ausnahmen als C++ Ausnahmen finden Sie unter [_set_se_translator](../c-runtime-library/reference/set-se-translator.md).

Wenn Sie strukturierte und C++ Ausnahmen miteinander mischen, beachten Sie diese potenziellen Probleme:

- C++-Ausnahmen und strukturierte Ausnahmen können nicht in derselben Funktion kombiniert werden.

- Beendigungs Handler ( **__finally** Blöcke) werden immer ausgeführt, auch während der Entwicklung, nachdem eine Ausnahme ausgelöst wurde.

- C++durch die Ausnahmebehandlung können Entlade Semantik in allen Modulen abgefangen und beibehalten werden, die mit den [/eh](../build/reference/eh-exception-handling-model.md) -Compileroptionen kompiliert werden, die eine Entlade Semantik ermöglichen.

- Es kann Situationen geben, in denen Destruktorfunktionen nicht für alle Objekte aufgerufen werden. Wenn z. b. eine strukturierte Ausnahme beim Versuch auftritt, einen Funktionsaufruf über einen nicht initialisierten Funktionszeiger durchführen, und diese Funktion als Parameter Objekte annimmt, die vor dem Aufruf erstellt wurden, werden die destrukturtoren dieser Objekte nicht aufgerufen. während der Stapel Entladung.

## <a name="next-steps"></a>Nächste Schritte

- [Verwenden von setjmp oder longjmp C++ in Programmen](../cpp/using-setjmp-longjmp.md)

  Weitere Informationen zur Verwendung von `setjmp` und `longjmp` in C++ Programmen finden Sie unter.

- [Behandeln strukturierter Ausnahmen in C++](../cpp/exception-handling-differences.md)

  Hier finden Sie Beispiele für die Vorgehensweise C++ , mit der Sie strukturierte Ausnahmen behandeln können.

## <a name="see-also"></a>Siehe auch

[Moderne C++ bewährte Methoden für Ausnahmen und Fehlerbehandlung](../cpp/errors-and-exception-handling-modern-cpp.md)
