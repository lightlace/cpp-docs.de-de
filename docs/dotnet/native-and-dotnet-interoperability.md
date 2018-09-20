---
title: Native und .NET Interoperabilität | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++]
- .NET Framework [C++], interoperability with Visual C++
- interoperability [C++], about .NET interoperability
- interop [C++], about .NET interoperability
- managed code [C++], interoperability
- native code [C++]
- interoperability [C++]
- MFC [C++], .NET integration
- unmanaged code interoperability [C++]
- Visual C++, interoperability
- native code [C++], .NET interoperatibility
ms.assetid: f3ec6c99-c745-4256-b95b-f1d12ba17a5a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a6f62ff29ce104362d3057773e09a3cea1f69eed
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420483"
---
# <a name="native-and-net-interoperability"></a>Interoperabilität von systemeigenem Code und .NET

Visual C++ unterstützt Interoperabilitätsfunktionen, die ein Nebeneinander von verwalteten und nicht verwalteten Konstrukten innerhalb der gleichen Assembly und sogar in der gleichen Datei erlauben. Ein Teil dieser Funktionalität, z. B. P/Invoke, wird zwar auch von anderen .NET-Programmiersprachen unterstützt, der Großteil der von Visual C++ bereitgestellten Interoperabilitätsunterstützung ist jedoch nicht in anderen Programmiersprachen verfügbar.

## <a name="in-this-section"></a>In diesem Abschnitt

[Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)<br/>
Beschreibt Assemblys, die mit generiert die [/CLR (Common Language Runtime Compilation)](../build/reference/clr-common-language-runtime-compilation.md) -Compileroption, die beide enthalten verwaltet und nicht verwaltete Funktionen.

[Verwenden eines Windows Form-Benutzersteuerelements in MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
Erläutert, wie Sie die MFC-Windows Forms-Unterstützungsklassen verwenden, um Windows Forms-Steuerelemente in einer MFC-Anwendung zu hosten.

[Aufrufen nativer Funktionen aus verwaltetem Code](../dotnet/calling-native-functions-from-managed-code.md)<br/>
Beschreibt, wie nicht-CLR-DLLs von .NET-Anwendungen verwendet werden können.

## <a name="see-also"></a>Siehe auch

