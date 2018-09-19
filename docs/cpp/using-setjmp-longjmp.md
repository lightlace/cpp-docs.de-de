---
title: Verwenden von Setjmp / Longjmp | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/14/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- longjmp_cpp
- setjmp_cpp
dev_langs:
- C++
helpviewer_keywords:
- C++ exception handling, setjmp/longjmp functions
- setjmpex.h
- longjmp function in C++ programs
- setjmp.h
- setjmp function
- setjmp function, C++ programs
ms.assetid: 96be8816-f6f4-4567-9a9c-0c3c720e37c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 711d829ea3393041c713fbb042318b680100a52a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111952"
---
# <a name="using-setjmp-and-longjmp"></a>Verwenden von Setjmp / longjmp

Wenn [Setjmp](../c-runtime-library/reference/setjmp.md) und [Longjmp](../c-runtime-library/reference/longjmp.md) werden zusammen verwendet werden, sie bieten eine Möglichkeit zum Ausführen eines nicht lokalen **Goto**. Sie werden in der Regel in C-Code verwendet, um die ausführungssteuerung an Fehlerbehandlungs- oder Wiederherstellungscode in einer vorher aufgerufenen Routine zu übergeben, ohne die standardmäßigen Aufruf- oder Rückgabekonventionen.

> [!CAUTION]
> Da `setjmp` und `longjmp` unterstützen nicht die ordnungsgemäße Zerstörung von Stack-Frame-Objekten zwischen C++-Compiler portabel und beeinträchtigen möglicherweise die Leistung durch Verhindern von Optimierung für lokale Variablen, wir nicht empfehlen, da deren Verwendung in C++ Programme. Es wird empfohlen, **versuchen** und **catch** stattdessen erstellt.

Wenn Sie verwenden möchten `setjmp` und `longjmp` in einem C++-Programm beinhalten auch \<setjmp.h > oder \<setjmpex.h > um ordnungsgemäße Interaktion zwischen den Funktionen und eine strukturierte Ausnahme behandeln (SEH) oder C++-Ausnahme zu gewährleisten. der Verarbeitung.

**Microsoft-spezifisch**

Bei Verwendung einer [/EH](../build/reference/eh-exception-handling-model.md) option, um C++-Code zu kompilieren, werden die Destruktoren für lokale Objekte während der stapelentladung aufgerufen. Allerdings bei Verwendung von **/EHs** oder **/EHsc** kompilieren und eine der Funktionen, die verwendet ["noexcept"](../cpp/noexcept-cpp.md) Aufrufe `longjmp`, und klicken Sie dann der Destruktor für diese Funktion entladen erfolgen möglicherweise keine, abhängig vom Optimierer Status.

In übertragbarem Code Wenn eine `longjmp` Aufruf ausgeführt wird, ordnungsgemäße Zerstörung von framebasierten Objekten nicht explizit durch den Standard garantiert ist, und möglicherweise von anderen Compilern nicht unterstützt. Um Sie auf der Warnstufe 4, einen Aufruf von informieren, dass `setjmp` bewirkt, dass die Warnung C4611: Interaktion zwischen "_setjmp" und C++-objektlöschung ist nicht portabel.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Kombination von C (strukturiert)- und C++-Ausnahmen](../cpp/mixing-c-structured-and-cpp-exceptions.md)
