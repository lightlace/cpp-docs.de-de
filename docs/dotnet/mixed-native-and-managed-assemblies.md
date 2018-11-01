---
title: Gemischte (systemeigene und verwaltete) Assemblys
ms.date: 09/18/2018
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
ms.openlocfilehash: 78e95177282804369bac2065582a06b8acbc975b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428675"
---
# <a name="mixed-native-and-managed-assemblies"></a>Gemischte (native und verwaltete) Assemblys

Gemischte Assemblys können sowohl nicht verwaltete Maschinenanweisungen als auch MSIL-Anweisungen enthalten. Dadurch können sie zum Aufrufen und die Beibehaltung der Kompatibilität mit nativen C++-Bibliotheken von .NET Komponenten, aufgerufen werden. Mit gemischten Assemblys können Entwickler Anwendungen mit einer Mischung von .NET- und systemeigenen C++-Code erstellen.

Beispielsweise kann eine vorhandene Bibliothek besteht ausschließlich aus systemeigenen C++-Code in die .NET-Plattform geschaltet werden, durch das erneute Kompilieren lediglich ein Modul mit dem **"/ CLR"** Compilerschalter. Dieses Modul kann dann .NET-Funktionen verwenden, bleibt aber mit dem Rest der Anwendung kompatibel. Es ist auch möglich, zum entscheiden zwischen verwalteten und nativen Kompilierung pro Funktion von innerhalb der gleichen Datei (finden Sie unter [verwaltete, unverwaltete](../preprocessor/managed-unmanaged.md)).

Visual C++ unterstützt die Generierung von gemischten verwalteten Assemblys nur mithilfe der **"/ CLR"** -Compileroption. Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden. Wenn Sie die reinen oder überprüfbare verwaltete Assemblys benötigen, empfehlen wir, dass Sie sie mithilfe von c# erstellen.

Frühere Versionen von Visual C++-Compiler-Toolsets unterstützt die Generierung von drei verschiedenen Typen verwalteter Assemblys: gemischte, reine und überprüfbare. Die letzten zwei finden Sie im [reiner und überprüfbarer Code (C++ / CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md).

## <a name="in-this-section"></a>In diesem Abschnitt

[Gewusst wie: Migrieren auf/CLR](../dotnet/how-to-migrate-to-clr.md)<br/>
Beschreibt die empfohlenen Schritte zum Einführen bzw. Aktualisieren der .NET-Funktionen in der Anwendung.

[Gewusst wie: Kompilieren von MFC und ATL-Code durch Verwendung von "/ CLR"](../dotnet/how-to-compile-mfc-and-atl-code-by-using-clr.md)<br/>
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

[Vermeiden von Ausnahmen beim CLR Herunterfahren bei erstellte COM-Objekte mit/CLR](../dotnet/avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr.md)<br/>
Behandelt das ordnungsgemäße Schließen einer verwalteten Anwendung sichergestellt wird, der ein COM-Objekt, das mit kompiliert nutzt **"/ CLR"**.

[Vorgehensweise: Erstellen einer teilweise vertrauenswürdigen Anwendung durch Entfernen der Abhängigkeit der CRT-Bibliotheks-DLL](../dotnet/create-a-partially-trusted-application.md)<br/>
Erläutert, wie zum Erstellen einer teilweise vertrauenswürdigen Common Language Runtime-Anwendung mit Visual C++ von der Abhängigkeit von msvcm90.dll aufgehoben.

Weitere Informationen über Codierungsrichtlinien für gemischte Assemblys finden Sie im MSDN-Artikel [An Overview of verwaltetem/nicht verwaltetem Code Interoperability](https://msdn.microsoft.com/library/ms973872.aspx).

## <a name="see-also"></a>Siehe auch

- [Interoperabilität von nativem Code und .NET](../dotnet/native-and-dotnet-interoperability.md)
