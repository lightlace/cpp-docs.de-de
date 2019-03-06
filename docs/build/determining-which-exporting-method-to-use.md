---
title: Bestimmen der geeigneten Exportmethode
ms.date: 11/04/2016
helpviewer_keywords:
- __declspec(dllexport) keyword [C++]
- exporting DLLs [C++], method comparison
- def files [C++], exporting from DLLs
- .def files [C++], exporting from DLLs
ms.assetid: 66d773ed-935c-45c2-ad03-1a060874b34d
ms.openlocfilehash: 38006acfae90c3b216677684e9776f3ed5d7c1b1
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422753"
---
# <a name="determining-which-exporting-method-to-use"></a>Bestimmen der geeigneten Exportmethode

Sie können Funktionen in einer der beiden Methoden exportieren – eine DEF-Datei oder das `__declspec(dllexport)` Schlüsselwort. Um zu entscheiden, welche Methode besser für die DLL ist, berücksichtigen Sie diese Fragen:

- Möchten Sie weitere Funktionen zu einem späteren Zeitpunkt exportieren?

- Ist Ihre DLL nur von Anwendungen verwendet wird, die Sie neu erstellen, können, oder sie von Anwendungen, die Sie neu erstellen, können nicht verwendet wird – z. B. Anwendungen, die von Drittanbietern erstellt werden?

## <a name="pros-and-cons-of-using-def-files"></a>Vor- und Nachteile der Verwendung von DEF-Dateien

Exportieren von Funktionen in einer DEF-Datei haben Sie die Kontrolle über die Exportordinalzahlen aus. Wenn Sie die DLL eine exportierte Funktion hinzugefügt haben, können Sie einen höheren Ordinalwert als alle anderen exportierten Funktionen zuweisen. Wenn Sie dies tun, müssen Anwendungen, die implizite Verknüpfung verwenden, nicht mit der Importbibliothek zu verknüpfen, die die neue Funktion enthält. Dies ist sehr praktisch, wenn Sie eine DLL für die Verwendung durch mehrere Anwendungen entwerfen werden, da Sie neue Funktionalität hinzufügen können, und stellen Sie außerdem sicher, dass sie weiterhin funktionieren ordnungsgemäß mit den Anwendungen, die bereits darauf basieren. Beispielsweise werden die MFC-DLLs mithilfe von DEF-Dateien erstellt.

Ein weiterer Vorteil von DEF-Datei ist, dass Sie verwenden können, die `NONAME` Attribut, um eine Funktion exportieren. Dadurch wird nur die Ordinalzahl an, in der Exporttabelle in der DLL. Für DLLs, die eine große Anzahl von exportierten Funktionen, die mit der `NONAME` Attribut kann die Größe der DLL-Datei verringern. Informationen dazu, wie Sie eine Modul-Definition-Anweisung zu schreiben, finden Sie unter [Regeln für Moduldefinitionsanweisungen](../build/reference/rules-for-module-definition-statements.md). Informationen zum Exportieren der Ordnungszahl finden Sie unter [Exportieren von Funktionen aus einer DLL über die Ordnungszahl statt über Namen](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).

Ein Nachteil der Verwendung einer DEF-Datei ist, wenn Sie Funktionen in einer C++-Datei exportieren, entweder die ergänzten Namen in der DEF stellen müssen, Datei zu definieren oder die exportierten Funktionen unter Verwendung von Extern "C", um die namensergänzung zu vermeiden, die durchgeführt wurde vom Visual C++-Compiler.

Wenn Sie die ergänzten Namen in der DEF-Datei einfügen, können Sie sie abrufen, indem Sie mit der [DUMPBIN](../build/reference/dumpbin-reference.md) tool oder mit der Linker [/MAP](../build/reference/map-generate-mapfile.md) Option. Die ergänzten Namen, die vom Compiler erstellt werden, sind compilerspezifisch; aus diesem Grund, wenn Sie die ergänzten Namen, die vom Compiler in eine DEF-Datei erstellt werden einfügen, die Anwendungen, die zur DLL verknüpfen müssen auch erstellt werden mithilfe der gleichen Version des Compilers, damit die ergänzten Namen in die aufrufende Anwendung das exportierte übereinstimmen Namen i n der DLL die DEF-Datei.

## <a name="pros-and-cons-of-using-declspecdllexport"></a>Vor- und Nachteile der Verwendung von "__declspec(dllexport)" "

Mithilfe von `__declspec(dllexport)` ist praktisch, da Sie nicht verfügen, um eine DEF-Datei und die ergänzten Namen der exportierten Funktionen kümmern. Die Nützlichkeit der auf diese Weise zu exportieren ist jedoch durch die Anzahl der verknüpften Anwendungen beschränkt, die Sie neu erstellen möchten. Wenn Sie die DLL mit neuen Exporten neu erstellen, müssen Sie auch die Anwendungen neu zu erstellen, da sich die ergänzten Namen für die exportierte C++-Funktionen ändern können, wenn Sie eine andere Version des Compilers verwenden, um es erneut zu erstellen.

### <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Exportieren Sie aus einer DLL. DEF-Dateien](../build/exporting-from-a-dll-using-def-files.md)

- [Exportieren Sie aus einer DLL mithilfe von __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)

- [Exportieren Sie und importieren Sie mithilfe von AFX_EXT_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)

- [Exportieren von C++-Funktionen für die Verwendung in ausführbaren c-Dateien](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Exportieren von C-Funktionen für die Verwendung in ausführbaren C oder C++-Dateien](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Importieren Sie in eine Anwendung mithilfe von "__declspec(dllimport)" "](../build/importing-into-an-application-using-declspec-dllimport.md)

- [Initialisieren einer DLL](../build/run-time-library-behavior.md#initializing-a-dll)

### <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [Importieren und Exportieren von Inlinefunktionen](../build/importing-and-exporting-inline-functions.md)

- [Gegenseitige Importe](../build/mutual-imports.md)

- [Ergänzte Namen](../build/reference/decorated-names.md)

## <a name="see-also"></a>Siehe auch

[Exportieren aus einer DLL](../build/exporting-from-a-dll.md)
