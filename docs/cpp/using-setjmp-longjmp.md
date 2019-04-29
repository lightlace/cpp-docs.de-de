---
title: Verwenden von Setjmp / longjmp
ms.date: 08/14/2018
f1_keywords:
- longjmp_cpp
- setjmp_cpp
helpviewer_keywords:
- C++ exception handling, setjmp/longjmp functions
- setjmpex.h
- longjmp function in C++ programs
- setjmp.h
- setjmp function
- setjmp function, C++ programs
ms.assetid: 96be8816-f6f4-4567-9a9c-0c3c720e37c5
ms.openlocfilehash: 4ead12f79701899b3977993c9de3c3803023150f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364518"
---
# <a name="using-setjmp-and-longjmp"></a>Verwenden von Setjmp / longjmp

Wenn [Setjmp](../c-runtime-library/reference/setjmp.md) und [Longjmp](../c-runtime-library/reference/longjmp.md) werden zusammen verwendet werden, sie bieten eine Möglichkeit zum Ausführen eines nicht lokalen **Goto**. Sie werden in der Regel in C-Code verwendet, um die ausführungssteuerung an Fehlerbehandlungs- oder Wiederherstellungscode in einer vorher aufgerufenen Routine zu übergeben, ohne die standardmäßigen Aufruf- oder Rückgabekonventionen.

> [!CAUTION]
> Da `setjmp` und `longjmp` unterstützen nicht die ordnungsgemäße Zerstörung von Stack-Frame-Objekten zwischen C++-Compiler portabel und beeinträchtigen möglicherweise die Leistung durch Verhindern von Optimierung für lokale Variablen, wir nicht empfehlen, da deren Verwendung in C++ Programme. Es wird empfohlen, **versuchen** und **catch** stattdessen erstellt.

Wenn Sie verwenden möchten `setjmp` und `longjmp` in einem C++-Programm beinhalten auch \<setjmp.h > oder \<setjmpex.h > um ordnungsgemäße Interaktion zwischen den Funktionen und eine strukturierte Ausnahme behandeln (SEH) oder C++-Ausnahme zu gewährleisten. der Verarbeitung.

**Microsoft-spezifisch**

Bei Verwendung einer [/EH](../build/reference/eh-exception-handling-model.md) option, um C++-Code zu kompilieren, werden die Destruktoren für lokale Objekte während der stapelentladung aufgerufen. Allerdings bei Verwendung von **/EHs** oder **/EHsc** kompilieren und eine der Funktionen, die verwendet ["noexcept"](../cpp/noexcept-cpp.md) Aufrufe `longjmp`, und klicken Sie dann der Destruktor für diese Funktion entladen erfolgen möglicherweise keine, abhängig vom Optimierer Status.

In übertragbarem Code Wenn eine `longjmp` Aufruf ausgeführt wird, ordnungsgemäße Zerstörung von framebasierten Objekten nicht explizit durch den Standard garantiert ist, und möglicherweise von anderen Compilern nicht unterstützt. Um Sie auf der Warnstufe 4, einen Aufruf von informieren, dass `setjmp` bewirkt, dass die Warnung C4611: Interaktion zwischen "_setjmp" und C++ objektlöschung ist nicht portabel.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Kombination von C (strukturiert)- und C++-Ausnahmen](../cpp/mixing-c-structured-and-cpp-exceptions.md)
