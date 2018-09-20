---
title: Ausnahmebehandlung (Komponentenerweiterungen für C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- structured exception handling [C++], managed exceptions
- Exception class, managed applications
- exception handling
- C++ exception handling
- exception handling, types of
- System::Exception class in managed applications
ms.assetid: ccb11fe8-6938-41ac-b477-a183e85865b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2213266d281933c6a6a59775584532acaeb39d6e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412319"
---
# <a name="exception-handling--c-component-extensions"></a>Ausnahmebehandlung (Komponentenerweiterungen für C++)

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
Beschreibt die Behandlung von Ausnahmen in C++.

## <a name="see-also"></a>Siehe auch

[Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)