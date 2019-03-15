---
title: Exportieren aus einer DLL
ms.date: 11/04/2016
helpviewer_keywords:
- exporting DLLs [C++], about exporting from DLLs
- exporting functions [C++], DLLs (exporting from)
- exporting DLLs [C++]
- DLLs [C++], exporting from
- DLL exports [C++]
- functions [C++], exporting
- exports table [C++]
ms.assetid: a08f86c4-5996-460b-ae54-da2b764045f0
ms.openlocfilehash: 6bdf5b86724ae07aa073a9feb1cc4d5723bc6e6b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57819117"
---
# <a name="exporting-from-a-dll"></a>Exportieren aus einer DLL

Das Layout einer DLL-Datei ähnelt dem einer EXE-Datei. Ein wichtiger Unterschied besteht jedoch darin, dass eine DLL-Datei über eine Exporttabelle verfügt. Die Exporttabelle umfasst die Namen aller Funktionen, die von der DLL in andere ausführbare Dateien exportiert werden. Die Funktionen sind Einstiegspunkte in die DLL. Andere ausführbare Dateien können nur auf die in der Exporttabelle genannten Funktionen zugreifen. Alle weiteren Funktionen in der DLL sind privat, d. h. ausschließlich auf die DLL bezogen. Die Exporttabelle einer DLL kann angezeigt werden, mithilfe der [DUMPBIN](reference/dumpbin-reference.md) Tool, mit der Option/Exports.

Es gibt zwei Methoden zum Exportieren von Funktionen aus einer DLL:

- Erzeugen Sie eine Moduldefinitionsdatei (.def), und verwenden Sie beim Erstellen der DLL diese DEF-Datei. Verwenden Sie diesen Ansatz, wenn Sie möchten [Exportieren von Funktionen aus einer DLL über die Ordnungszahl statt über den Namen](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).

- Verwenden Sie das Schlüsselwort **__declspec(dllexport)** in die Definition der Funktion.

Wenn Funktionen mit beiden Methoden exportieren, sollten Sie verwenden die [__stdcall](../cpp/stdcall.md) Aufrufkonvention.

## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Exportieren Sie aus einer DLL mithilfe von DEF-Dateien](exporting-from-a-dll-using-def-files.md)

- [Exportieren Sie aus einer DLL mithilfe von __declspec(dllexport)](exporting-from-a-dll-using-declspec-dllexport.md)

- [Exportieren Sie und importieren Sie mithilfe von AFX_EXT_CLASS](exporting-and-importing-using-afx-ext-class.md)

- [Exportieren von C++-Funktionen für die Verwendung in ausführbaren c-Dateien](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Exportieren von C-Funktionen für die Verwendung in ausführbaren C oder C++-Dateien](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Exportieren von Funktionen aus einer DLL über die Ordnungszahl statt über den Namen](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)

- [Bestimmen Sie die Exportmethode verwendet werden](determining-which-exporting-method-to-use.md)

- [Link an executable to a DLL (Eine ausführbare Datei mit einer DLL verknüpfen)](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

- [Initialisieren einer DLL](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [Importieren in eine Anwendung](importing-into-an-application.md)

- [Importieren und Exportieren von Inlinefunktionen](importing-and-exporting-inline-functions.md)

- [Gegenseitige Importe](mutual-imports.md)

## <a name="see-also"></a>Siehe auch

[Importieren und Exportieren](importing-and-exporting.md)
