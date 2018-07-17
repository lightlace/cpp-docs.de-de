---
title: Gemischte (systemeigene und verwaltete) Assemblys | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], mixed assemblies
- /clr compiler option [C++], mixed assemblies
- managed code [C++], interoperability
- interoperability [C++], mixed assemblies
- mixed DLL loading [C++]
- mixed assemblies [C++], about mixed assemblies
- assemblies [C++], mixed
- mixed assemblies [C++]
- native code [C++], .NET interoperatibility
ms.assetid: 4299dfce-392f-4933-8bf0-5da2f0d1c282
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 469e0429408e1b8afed65889539202650cd28413
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704788"
---
# <a name="mixed-native-and-managed-assemblies"></a>Gemischte (systemeigene und verwaltete) Assemblys

Gemischte Assemblys können sowohl nicht verwaltete Maschinenanweisungen als auch MSIL-Anweisungen enthalten. Dadurch können sie .NET-Komponenten aufrufen und von ihnen aufgerufen werden, wobei die Kompatibilität mit vollständig nicht verwalteten Komponenten erhalten bleibt. Mit gemischten Assemblys können Entwickler Anwendungen mit einer Mischung aus verwalteten und nicht verwalteten Funktionen erstellen. Deshalb sind gemischte Assemblys optimal für das Migrieren von vorhandenen Visual C++-Anwendungen zur .NET-Plattform geeignet.

Beispielsweise kann eine vorhandene Anwendung, die vollständig aus nicht verwalteten Funktionen besteht in die .NET-Plattform geschaltet werden, durch das erneute Kompilieren lediglich ein Modul mit der **"/ CLR"** Compilerschalter. Dieses Modul kann dann .NET-Funktionen verwenden, bleibt aber mit dem Rest der Anwendung kompatibel. Dadurch kann eine Anwendung schrittweise in die .NET-Plattform konvertiert werden. Es ist sogar möglich, um zu entscheiden, zwischen verwaltetem und nicht verwaltetem Kompilierung in Abständen von Funktion innerhalb der gleichen Datei (siehe [verwaltete, unverwaltete](../preprocessor/managed-unmanaged.md)).

Visual C++ unterstützt das Generieren von gemischten verwalteten Assemblys nur mithilfe der **"/ CLR"** -Compileroption. Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden. Wenn Sie die reinen oder überprüfbar verwaltete Assemblys benötigen, empfehlen wir, dass Sie mithilfe von c# erstellen.

Frühere Versionen von Visual C++-Compilertoolset unterstützt die Generierung von drei verschiedenen Typen verwalteter Assemblys: gemischte, reine und überprüfbare. Die letzten zwei finden Sie im Abschnitt [reiner und überprüfbarer Code (C + c++ / CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md).

## <a name="in-this-section"></a>In diesem Abschnitt

[Vorgehensweise: Migrieren auf/CLR](../dotnet/how-to-migrate-to-clr.md)<br/>
Beschreibt die empfohlenen Schritte zum Einführen bzw. Aktualisieren der .NET-Funktionen in der Anwendung.

[Vorgehensweise: Kompilieren von MFC und ATL-Code durch Verwenden von "/ CLR"](../dotnet/how-to-compile-mfc-and-atl-code-by-using-clr.md)<br/>
Erläutert, wie vorhandene MFC- und ATL-Programme für die Common Language Runtime kompiliert werden können.

[Initialisierung gemischter Assemblys](../dotnet/initialization-of-mixed-assemblies.md)<br/>
Beschreibt das Problem der "Ladeprogrammsperren" und die entsprechenden Lösungen.

[Bibliotheksunterstützung für verschiedene Assemblys](../dotnet/library-support-for-mixed-assemblies.md)<br/>
Erläutert, wie systemeigene Bibliotheken in **"/ CLR"** Kompilierungen.

[Überlegungen zur Leistung](../dotnet/performance-considerations-for-interop-cpp.md)<br/>
Beschreibt, wie sich gemischte Assemblys und das Marshalling von Daten auf die Leistung auswirken.

[Anwendungsdomänen und Visual C++](../dotnet/application-domains-and-visual-cpp.md)<br/>
Erörtert die Visual C++-Unterstützung für Anwendungsdomänen.

[Doppeltes Thunking](../dotnet/double-thunking-cpp.md)<br/>
Erörtert, wie sich ein systemeigener Einstiegspunkt für eine verwaltete Funktion auf die Leistung auswirkt.

[Vermeiden von Ausnahmen beim CLR Herunterfahren bei erstellte COM-Objekte mit "/ CLR"](../dotnet/avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr.md)<br/>
Erläutert das ordnungsgemäße Schließen einer verwalteten Anwendung sichergestellt ist, die ein COM-Objekt, das mit kompiliert nutzt **"/ CLR"**.

[Vorgehensweise: Erstellen einer teilweise vertrauenswürdigen Anwendung durch Entfernen der Abhängigkeit der CRT-Bibliotheks-DLL](../dotnet/create-a-partially-trusted-application.md)<br/>
Erläutert das Erstellen einer teilweise vertrauenswürdigen Common Language Runtime-Anwendung, indem Sie in Visual C++ Abhängigkeit von msvcm90.dll aufgehoben.

Weitere Informationen zu Codierungsrichtlinien bei gemischten Assemblys, finden Sie im MSDN-Artikel [eine Übersicht über die der verwaltete/nicht verwaltete Codeinteroperabilität](https://msdn.microsoft.com/en-us/library/ms973872.aspx).

## <a name="see-also"></a>Siehe auch

- [Interoperabilität von nativem Code und .NET](../dotnet/native-and-dotnet-interoperability.md)
