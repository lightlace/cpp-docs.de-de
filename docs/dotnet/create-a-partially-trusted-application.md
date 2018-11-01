---
title: 'Vorgehensweise: Erstellen einer teilweise vertrauenswürdigen Anwendung (C++ / CLI)'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- partially trusted applications [C++]
- mixed assemblies [C++], partially trusted applications
- msvcm90[d].dll
- interoperability [C++], partially trusted applications
- interop [C++], partially trusted applications
- /clr compiler option [C++], partially trusted applications
ms.assetid: 4760cd0c-4227-4f23-a7fb-d25b51bf246e
ms.openlocfilehash: fb65c8ff3dc4c3b03fa319fd1e7a6eb95f11bef2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445967"
---
# <a name="how-to-create-a-partially-trusted-application-by-removing-dependency-on-the-crt-library-dll"></a>Gewusst wie: Erstellen einer teilweise vertrauenswürdigen Anwendung durch Entfernen der Abhängigkeit der CRT-Bibliotheks-DLL

In diesem Thema wird erläutert, wie zum Erstellen einer teilweise vertrauenswürdigen Common Language Runtime-Anwendung mit Visual C++ von der Abhängigkeit von msvcm90.dll aufgehoben wird.

Erstellt mit Visual C++-Anwendung **"/ CLR"** weist eine Abhängigkeit von msvcm90.dll abhängig, die Teil der C-Laufzeitbibliothek ist. Wenn Sie Ihre Anwendung in einer teilweise vertrauenswürdigen Umgebung verwendet werden soll, wird die CLR bestimmte Regeln für die Codezugriffssicherheit auf die DLL erzwungen. Aus diesem Grund ist es erforderlich sein, diese Abhängigkeit zu entfernen, da msvcm90.dll systemeigenen Code enthält und die Codezugriff-Sicherheitsrichtlinie nicht, darauf erzwungen werden.

Wenn Ihre Anwendung keine Funktionen der C-Laufzeitbibliothek verwendet und die Abhängigkeit von dieser Bibliothek aus dem Code entfernen möchten, müssen Sie verwenden die **/NODEFAULTLIB:msvcmrt.lib** (Linkeroption) und einen Link mit ptrustm.lib oder ptrustmd.lib. Diese Bibliotheken enthalten, die Objektdateien für die Initialisierung und Initialisierung einer Anwendung, Ausnahmeklassen, die von den Initialisierungscode verwendet und verwalteten Code zur Ausnahmebehandlung. Verknüpfen mit einer dieser Bibliotheken entfernt jede Abhängigkeit von msvcm90.dll aufgehoben.

> [!NOTE]
>  Die Reihenfolge der Initialisierung der Assembly unterscheiden sich für Anwendungen, die die Ptrust-Bibliotheken verwenden. Für normale Anwendungen werden Assemblys in der Regel entladen in umgekehrter Reihenfolge, die sie geladen werden, aber dies ist nicht gewährleistet. Für teilweise vertrauenswürdige Anwendungen werden die Assemblys in der Regel in der gleichen Reihenfolge entladen, dass sie geladen werden. Dies ist auch nicht garantiert.

### <a name="to-create-a-partially-trusted-mixed-clr-application"></a>Erstellung einer teilweise vertrauenswürdigen gemischt (/ Clr) Anwendung

1. Um die Abhängigkeit von msvcm90.dll zu entfernen, geben Sie für den Linker nicht durch die Verwendung dieser Bibliothek einbeziehen der **/NODEFAULTLIB:msvcmrt.lib** -Linkeroption. Informationen zum dazu verwenden Sie die Entwicklungsumgebung von Visual Studio oder programmgesteuert, finden Sie unter [/NODEFAULTLIB (Bibliotheken ignorieren)](../build/reference/nodefaultlib-ignore-libraries.md).

1. Fügen Sie eine der Ptrustm-Bibliotheken, auf die Linker-Eingabe-Abhängigkeiten. Verwenden Sie ptrustm.lib, wenn Sie Ihre Anwendung im Releasemodus erstellen. Verwenden Sie für den Debugmodus ptrustmd.lib. Informationen zum dazu verwenden Sie die Entwicklungsumgebung von Visual Studio oder programmgesteuert, finden Sie unter [. LIB-Dateien als Linkereingabe](../build/reference/dot-lib-files-as-linker-input.md).

## <a name="see-also"></a>Siehe auch

[Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)<br/>
[Initialisierung gemischter Assemblys](../dotnet/initialization-of-mixed-assemblies.md)<br/>
[Bibliotheksunterstützung für verschiedene Assemblys](../dotnet/library-support-for-mixed-assemblies.md)<br/>
[/link (Optionen an Linker übergeben)](../build/reference/link-pass-options-to-linker.md)
