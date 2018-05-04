---
title: Bestimmen der geeigneten Exportmethode zu verwendenden | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __declspec(dllexport) keyword [C++]
- exporting DLLs [C++], method comparison
- def files [C++], exporting from DLLs
- .def files [C++], exporting from DLLs
ms.assetid: 66d773ed-935c-45c2-ad03-1a060874b34d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03c88cee3504d8efef8f9ca19073ed06b66f6aeb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="determining-which-exporting-method-to-use"></a>Bestimmen der geeigneten Exportmethode
Sie können Funktionen in einer der beiden Methoden exportieren – eine DEF-Datei oder das `__declspec(dllexport)` Schlüsselwort. Um Ihnen die Entscheidung, welche Möglichkeit besser für die DLL ist, berücksichtigen Sie diese Fragen:  
  
-   Möchten Sie später weitere Funktionen exportieren?  
  
-   Ihre DLL nur von Anwendungen, die Sie neu erstellen, können, oder wird es von Anwendungen verwendet, die Sie neu erstellen, können nicht verwendet wird – z. B. Anwendungen, die von Drittanbietern erstellt werden?  
  
## <a name="pros-and-cons-of-using-def-files"></a>Vor- und Nachteile der Verwendung von DEF-Dateien  
 Exportieren von Funktionen in einer DEF-Datei-ermöglicht Ihnen die Kontrolle über die Exportordinalzahlen aus. Wenn Sie die DLL eine exportierte Funktion hinzugefügt haben, können Sie einen höheren Ordinalwert als jede andere exportierten Funktion zuweisen. Wenn Sie dies tun, müssen Anwendungen, die implizite Verknüpfung verwenden nicht mit der Importbibliothek zu verknüpfen, die die neue Funktion enthält. Dies ist sehr praktisch, wenn Sie eine DLL für die Verwendung von vielen Anwendungen entwerfen, da Sie neue Funktionalität hinzufügen können, und stellen Sie außerdem sicher, dass es weiterhin mit den Anwendungen ordnungsgemäß funktioniert, die bereits von ihr abhängen. Beispielsweise sind die MFC-DLLs mithilfe von DEF-Dateien erstellt.  
  
 Ein weiterer Vorteil der über eine DEF-Datei ist, dass Sie verwenden können, die `NONAME` Attribut, um eine Funktion exportieren. Mit dieser Option wird nur die Ordinalzahl in der Exporttabelle in der DLL. Für DLLs, die eine große Anzahl von exportierten Funktionen aufweisen, die mit der `NONAME` Attribut kann die Größe der DLL-Datei verringern. Weitere Informationen dazu, wie ein Modul definitionsanweisung zu schreiben, finden Sie unter [Regeln für Moduldefinitionsanweisungen](../build/reference/rules-for-module-definition-statements.md). Informationen zum Exportieren der Ordnungszahl finden Sie unter [Exportieren von Funktionen aus einer DLL über die Ordnungszahl statt über den Namen](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).  
  
 Ein Nachteil von über eine DEF-Datei ist, wenn Sie Funktionen in einer C++-Datei exportieren, entweder die ergänzten Namen in der DEF gelegt haben, Datei definieren oder die exportierten Funktionen mithilfe von "extern"C"" die namensergänzung zu vermeiden, die durchgeführt hat vom Visual C++-Compiler.  
  
 Wenn Sie die ergänzten Namen in der DEF-Datei einfügen, erhalten Sie sie mithilfe der [DUMPBIN](../build/reference/dumpbin-reference.md) -tool oder mit der Linker [/MAP](../build/reference/map-generate-mapfile.md) Option. Die ergänzten Namen, die vom Compiler erstellt werden, sind compilerspezifisch. daher, wenn Sie die ergänzten Namen, die vom Compiler in eine DEF-Datei erstellt werden einfügen, die Anwendungen, die mit der DLL verknüpft müssen auch erstellt werden mithilfe der gleichen Version des Compilers, damit die ergänzten Namen in der aufrufenden Anwendung der exportierte übereinstimmen benennt i n der DLL die DEF-Datei.  
  
## <a name="pros-and-cons-of-using-declspecdllexport"></a>Vor- und Nachteile der Verwendung von __declspec(dllexport)  
 Mithilfe von `__declspec(dllexport)` liegt daran, dass Sie keine Gedanken machen, eine DEF-Datei und die ergänzten Namen der exportierten Funktionen. Allerdings wird die Nützlichkeit der auf diese Weise Exportieren von durch die Anzahl der verknüpften Anwendungen beschränkt, die Sie neu erstellen möchten. Wenn Sie die DLL mit neuen Exporten neu erstellen, müssen Sie auch die Anwendungen neu erstellen, da die ergänzten Namen für exportierte C++-Funktionen ändern können, wenn Sie eine andere Version des Compilers verwenden, um ihn neu erstellen.  
  
### <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?  
  
-   [Exportieren Sie aus einer DLL verwenden. DEF-Dateien](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exportieren Sie aus einer DLL mithilfe von __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Exportieren Sie und importieren Sie mithilfe von AFX_EXT_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Exportieren von C++-Funktionen zur Verwendung in ausführbaren c-Dateien](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Exportieren von C-Funktionen zur Verwendung in ausführbaren C oder C++-Dateien](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Importieren Sie in eine Anwendung mithilfe von "__declspec(dllimport)" "](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Initialisieren einer DLL](../build/run-time-library-behavior.md#initializing-a-dll)  
  
### <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [Importieren und Exportieren von Inlinefunktionen](../build/importing-and-exporting-inline-functions.md)  
  
-   [Gegenseitige Importe](../build/mutual-imports.md)  
  
-   [Ergänzte Namen](../build/reference/decorated-names.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Exportieren aus einer DLL](../build/exporting-from-a-dll.md)