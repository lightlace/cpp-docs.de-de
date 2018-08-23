---
title: Kombination von C (strukturierte) und C++-Ausnahmen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/14/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- exceptions [C++], mixed C and C++
- C++ exception handling, mixed-language
- structured exception handling [C++], mixed C and C++
- catch keyword [C++], mixed
- try-catch keyword [C++], mixed-language
ms.assetid: a149154e-36dd-4d1a-980b-efde2a563a56
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 580fb4c96db70b612135ac48e30bd9c0d45c4d1c
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2018
ms.locfileid: "42573253"
---
# <a name="mixing-c-structured-and-c-exceptions"></a>Kombination von C (strukturierte) und C++-Ausnahmen

Wenn Sie portablen Code schreiben möchten, nicht die Verwendung der strukturierten Ausnahmebehandlung (SEH) in einem C++-Programm empfohlen. Allerdings unter Umständen möchten Sie Kompilieren mit der [/EHa](../build/reference/eh-exception-handling-model.md) und strukturierte Ausnahmen und C++-Quellcode kombinieren und benötigen daher einige Funktionen zur Behandlung beider Arten von Ausnahmen. Da ein strukturierter Ausnahmehandler kein Konzept für die Objekte oder von typisierten Ausnahmen verfügt, kann es von C++-Code ausgelöste Ausnahmen nicht behandeln. Jedoch C++ **catch** Handler können strukturierte Ausnahmen behandeln. C++-ausnahmebehandlungssyntax (**versuchen**, **auslösen**, **catch**) wird nicht akzeptiert, durch den C-Compiler, aber strukturierte ausnahmebehandlungssyntax (**__try**, **__except**, **__finally**) wird von der C++-Compiler unterstützt.

Finden Sie unter [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) Informationen zur Behandlung strukturierte Ausnahmen als C++-Ausnahmen.

Wenn Sie strukturierte kombinieren und C++-Ausnahmen, die dieser potenziellen Probleme berücksichtigen:

- C++-Ausnahmen und strukturierte Ausnahmen können nicht in derselben Funktion kombiniert werden.

- Beendigungshandler (**__finally** Blöcke) werden immer ausgeführt, sogar während des Entladens, nachdem eine Ausnahme ausgelöst wird.

- C++-Ausnahmebehandlung kann abfangen und Beibehalten von entladungssemantik in allen Modulen mit kompiliert die [/EH](../build/reference/eh-exception-handling-model.md) Compileroptionen, die Entladesemantik für welche aktivieren.

- Es kann Situationen geben, in denen Destruktorfunktionen nicht für alle Objekte aufgerufen werden. Z. B. wenn eine strukturierte Ausnahme tritt auf, bei dem Versuch, eine Funktion über einen nicht initialisierten Funktionszeiger aufrufen und diese Funktion Objekte als Parameter nutzt, die vor dem Aufruf erstellt wurden, die Destruktoren dieser Objekte nicht heißen während der stapelentladung.

## <a name="next-steps"></a>Nächste Schritte

- [Verwenden von Setjmp oder Longjmp in C++-Programmen](../cpp/using-setjmp-longjmp.md)

  Finden Sie weitere Informationen zur Verwendung von `setjmp` und `longjmp` in C++-Programmen.

- [Strukturierte Ausnahmebehandlung in C++](../cpp/exception-handling-differences.md)

  Finden Sie Beispiele für die Möglichkeiten zum Ausnahmen behandeln, die strukturierte C++ verwendet werden können.

## <a name="see-also"></a>Siehe auch

[C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)  
