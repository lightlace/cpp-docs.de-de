---
title: Aufrufkonventionen
ms.date: 11/04/2016
helpviewer_keywords:
- calling conventions
ms.assetid: 11b1e45c-8fd1-420b-bca0-a19e294c1d85
ms.openlocfilehash: cc79a0636f900aa49e31f0dc35ee19657c3e1ccb
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345123"
---
# <a name="calling-conventions"></a>Aufrufkonventionen

Der Compiler für Visual C/C++ stellt mehrere unterschiedliche Konventionen für das Aufrufen von internen und externen Funktionen bereit. Das Verständnis dieser verschiedenen Ansätze hilft Ihnen, Ihr Programm zu debuggen und den Code mit Routinen in Assemblysprache zu verknüpfen.

In diesen Themen werden die Unterschiede zwischen den Aufrufkonventionen, wie Argumente übergeben werden und wie Werte über Funktionen zurückgegeben werden, erläutert. Es werden auch reine Funktionsaufrufe, eine erweiterte Funktion, die es erlaubt, Ihren eigenen Einleitungs- und Epilogcode zu schreiben, besprochen.

Informationen zu den Aufrufkonventionen für X64-Prozessoren finden Sie unter [Aufrufkonvention](../build/x64-calling-convention.md).

## <a name="topics-in-this-section"></a>Themen in diesem Abschnitt

- [Argumentübergabe und Benennungskonventionen](../cpp/argument-passing-and-naming-conventions.md) (`__cdecl`, `__stdcall`, `__fastcall`, usw.)

- [Aufrufbeispiel: Funktionsprototyp und Aufruf](../cpp/calling-example-function-prototype-and-call.md)

- [Verwendung von naked-Funktionsaufrufe, um benutzerdefinierte Prolog-und Epilogcode zu schreiben.](../cpp/naked-function-calls.md)

- [Gleitkomma-Coprozessor und Aufrufkonventionen](../cpp/floating-point-coprocessor-and-calling-conventions.md)

- [Veraltete Aufrufkonventionen](../cpp/obsolete-calling-conventions.md)

## <a name="see-also"></a>Siehe auch

[Microsoft-spezifische Modifizierer](../cpp/microsoft-specific-modifiers.md)