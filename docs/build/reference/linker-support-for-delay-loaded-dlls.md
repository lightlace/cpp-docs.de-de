---
title: Linkerunterstützung für verzögertes Laden von DLLs
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, linker support
ms.assetid: b2d7e449-2809-42b1-9c90-2c0ca5e31a14
ms.openlocfilehash: 384ea563853906a76e2c9993cbcedb3b15c354f2
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65217589"
---
# <a name="linker-support-for-delay-loaded-dlls"></a>Linkerunterstützung für verzögertes Laden von DLLs

Der Linker MSVC unterstützt jetzt das verzögerte Laden von DLLs. So müssen Sie die Windows SDK-Funktionen verwenden, müssen **LoadLibrary** und **GetProcAddress** implementieren das verzögerte Laden von DLLs.

Vor Visual C++ 6.0, Bestand die einzige Möglichkeit zum Laden einer DLL zur Laufzeit mithilfe von **LoadLibrary** und **GetProcAddress**; das Betriebssystem lädt die DLL bei der die ausführbare Datei oder DLL mit dem es geladen wurde.

Ab Visual C++ 6.0 wird beim implizit mit einer DLL verknüpfen, enthält den Linker an, dass die Optionen, um die Verzögerung Laden der DLL, bis das Programm die DLL eine Funktion aufruft.

Eine Anwendung kann verzögert werden Laden einer DLL mithilfe der [/DELAYLOAD (Laden von Import verzögern)](delayload-delay-load-import.md) Linkeroption mit eine Hilfsfunktion (Standardimplementierung von Visual C++). Die Hilfsfunktion lädt die DLL zur Laufzeit durch Aufrufen von **LoadLibrary** und **GetProcAddress** für Sie.

Berücksichtigen Sie verzögertes Laden einer DLL, wenn ein:

- Das Programm möglicherweise nicht auf eine Funktion in der DLL aufrufen.

- Eine Funktion in der DLL kann nicht bis spät in der programmausführung aufgerufen werden.

Das verzögerte Laden einer DLL kann angegeben werden, während des Buildvorgangs entweder ein. EXE-Datei oder. DLL-Projekt. EIN. DLL-Projekt, die das Laden von DLLs für eine oder mehrere verzögert sollten nicht selbst einen verzögert geladene Einstiegspunkt in Dllmain aufrufen.

Die folgenden Themen beschreiben das verzögerte Laden von DLLs:

- [Festlegen von DLLs für verzögertes Laden](specifying-dlls-to-delay-load.md)

- [Explizites Entladen einer verzögert geladenen DLL](explicitly-unloading-a-delay-loaded-dll.md)

- [Laden aller Importe für eine verzögert geladene DLL](loading-all-imports-for-a-delay-loaded-dll.md)

- [Binden von Importen](binding-imports.md)

- [Fehlerbehandlung und Benachrichtigung](error-handling-and-notification.md)

- [Sichern von verzögert geladenen Importen](dumping-delay-loaded-imports.md)

- [Beschränkungen für das verzögerte Laden von DLLs](constraints-of-delay-loading-dlls.md)

- [Die Hilfsfunktion](understanding-the-helper-function.md)

- [Entwickeln eigener Hilfsfunktionen](developing-your-own-helper-function.md)

## <a name="see-also"></a>Siehe auch

[Erstellen von C/C++-DLLs in Visual Studio](../dlls-in-visual-cpp.md)<br/>
[MSVC-Linkerreferenz](linking.md)
