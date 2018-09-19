---
title: Linkerunterstützung für verzögertes Laden von DLLs | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, linker support
ms.assetid: b2d7e449-2809-42b1-9c90-2c0ca5e31a14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 555a46ee65a5d5d5565128a15af01a2c1cf18540
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45711903"
---
# <a name="linker-support-for-delay-loaded-dlls"></a>Linkerunterstützung für verzögertes Laden von DLLs

Visual C++-Linker unterstützt jetzt das verzögerte Laden von DLLs. So müssen Sie die Windows SDK-Funktionen verwenden, müssen **LoadLibrary** und **GetProcAddress** implementieren das verzögerte Laden von DLLs.

Vor Visual C++ 6.0, Bestand die einzige Möglichkeit zum Laden einer DLL zur Laufzeit mithilfe von **LoadLibrary** und **GetProcAddress**; das Betriebssystem lädt die DLL bei der die ausführbare Datei oder DLL mit dem es geladen wurde.

Ab Visual C++ 6.0 wird beim statisch mit einer DLL verknüpfen, enthält den Linker an, dass die Optionen, um die Verzögerung Laden der DLL, bis das Programm die DLL eine Funktion aufruft.

Eine Anwendung kann verzögert werden Laden einer DLL mithilfe der [/DELAYLOAD (Laden von Import verzögern)](../../build/reference/delayload-delay-load-import.md) Linkeroption mit eine Hilfsfunktion (Standardimplementierung von Visual C++). Die Hilfsfunktion lädt die DLL zur Laufzeit durch Aufrufen von **LoadLibrary** und **GetProcAddress** für Sie.

Berücksichtigen Sie verzögertes Laden einer DLL, wenn ein:

- Das Programm möglicherweise nicht auf eine Funktion in der DLL aufrufen.

- Eine Funktion in der DLL kann nicht bis spät in der programmausführung aufgerufen werden.

Das verzögerte Laden einer DLL kann angegeben werden, während des Buildvorgangs entweder ein. EXE-Datei oder. DLL-Projekt. EIN. DLL-Projekt, die das Laden von DLLs für eine oder mehrere verzögert sollten nicht selbst einen verzögert geladene Einstiegspunkt in Dllmain aufrufen.

Die folgenden Themen beschreiben das verzögerte Laden von DLLs:

- [Festlegen von DLLs für verzögertes Laden](../../build/reference/specifying-dlls-to-delay-load.md)

- [Explizites Entladen einer verzögert geladenen DLL](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)

- [Laden aller Importe für eine verzögert geladene DLL](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md)

- [Binden von Importen](../../build/reference/binding-imports.md)

- [Fehlerbehandlung und Benachrichtigung](../../build/reference/error-handling-and-notification.md)

- [Sichern von verzögert geladenen Importen](../../build/reference/dumping-delay-loaded-imports.md)

- [Beschränkungen für das verzögerte Laden von DLLs](../../build/reference/constraints-of-delay-loading-dlls.md)

- [Die Hilfsfunktion](understanding-the-helper-function.md)

- [Entwickeln eigener Hilfsfunktionen](../../build/reference/developing-your-own-helper-function.md)

## <a name="see-also"></a>Siehe auch

[DLLs in Visual C++](../../build/dlls-in-visual-cpp.md)<br/>
[Verknüpfen](../../build/reference/linking.md)