---
title: Behandlung von Ausnahmen (C++ / CLI und C++ / CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- structured exception handling [C++], managed exceptions
- Exception class, managed applications
- exception handling
- C++ exception handling
- exception handling, types of
- System::Exception class in managed applications
ms.assetid: ccb11fe8-6938-41ac-b477-a183e85865b9
ms.openlocfilehash: 8886480b6f4497d042c6dd79dc2215887b84fceb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505026"
---
# <a name="exception-handling--ccli-and-ccx"></a>Behandlung von Ausnahmen (C++ / CLI und C++ / CX)

Anwendungen kompiliert wird, mit der `/ZW` Compileroption oder `/clr` Compileroption, die beide verwenden *Ausnahmen* , unerwartete Fehler während der Ausführung des Programms zu behandeln. Die folgenden Themen wird erläutert, für die Ausnahmebehandlung in beiden C++ / CX- oder C++ / CLI-Anwendungen.

## <a name="in-this-section"></a>In diesem Abschnitt

[Grundlegende Konzepte zur Verwendung verwalteter Ausnahmen](../dotnet/basic-concepts-in-using-managed-exceptions.md)<br/>
Beschreibt, Auslösen von Ausnahmen, und Verwenden von **versuchen**/**catch** Blöcke.

[Unterschiede im Ausnahmebehandlungsverhalten unter/CLR](../dotnet/differences-in-exception-handling-behavior-under-clr.md)<br/>
Erläutert die Unterschiede in das Standardverhalten der C++-Ausnahmebehandlung.

[finally](../dotnet/finally.md)<br/>
Erläutert, wie die finally-Schlüsselwort.

[Vorgehensweise: Definieren und Installieren eines globalen Ausnahmehandlers](../dotnet/how-to-define-and-install-a-global-exception-handler.md)<br/>
Veranschaulicht, wie nicht behandelte Ausnahmen erfasst werden können.

[Vorgehensweise: Abfangen von Ausnahmen, die von der MSIL ausgelöst wurden, in nativem Code](../dotnet/how-to-catch-exceptions-in-native-code-thrown-from-msil.md)<br/>
Erläutert, wie zum Abfangen von CLR und C++-Ausnahmen in systemeigenem Code.

[Vorgehensweise: Definieren und Installieren eines globalen Ausnahmehandlers](../dotnet/how-to-define-and-install-a-global-exception-handler.md)<br/>
Veranschaulicht, wie nicht behandelte Ausnahmen abgefangen.

## <a name="related-sections"></a>Verwandte Abschnitte

[Ausnahmebehandlung](../cpp/exception-handling-in-visual-cpp.md)<br/>
Beschreibt die Behandlung von Ausnahmen in C++-Standardbibliothek.

## <a name="see-also"></a>Siehe auch

[Komponentenerweiterungen für .NET und UWP](../windows/component-extensions-for-runtime-platforms.md)