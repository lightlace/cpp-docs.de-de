---
title: Exportieren aus einer DLL mithilfe von DEF-Dateien
ms.date: 11/04/2016
helpviewer_keywords:
- def files [C++], exporting from DLLs
- .def files [C++], exporting from DLLs
- exporting DLLs [C++], DEF files
ms.assetid: 9d31eda2-184e-47de-a2ee-a93ebd603f8e
ms.openlocfilehash: e4351d8eca6c6c580430aa8988344bf7f57e0a9f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50553906"
---
# <a name="exporting-from-a-dll-using-def-files"></a>Exportieren aus einer DLL mithilfe von DEF-Dateien

Eine Moduldefinitionsdatei (.def) ist eine Textdatei mit einer oder mehreren Modulanweisungen, die verschiedene Attribute einer DLL beschreiben. Wenn Sie nicht verwenden, werden die **"__declspec(dllexport)" "** Schlüsselwort zum Exportieren von DLL Funktionen die DLL benötigt eine DEF-Datei.

Eine DEF-Datei muss mindestens die folgenden Moduldefinitionsanweisungen enthalten:

- Die erste Anweisung in der Datei muss die LIBRARY-Anweisung sein. Sie kennzeichnet die Zugehörigkeit der DEF-Datei zu einer DLL. Auf die LIBRARY-Anweisung folgt der Name der DLL. Der Linker speichert diesen Namen in der Importbibliothek der DLL.

- Durch die EXPORTS-Anweisung werden die Namen und optional die Ordinalwerte der von der DLL exportierten Funktionen aufgelistet. Sie weisen der Funktion einen Ordinalwert zu, indem Sie dem Funktionsnamen ein @-Zeichen und eine Zahl nachstellen. Die Ordinalzahlen müssen sich in einem Bereich von 1 bis N befinden, wobei N die Gesamtzahl der von der DLL exportierten Funktionen angibt. Wenn Sie Funktionen anhand der Ordinalzahl exportieren möchten, finden Sie unter [Exportieren von Funktionen aus einer DLL über die Ordnungszahl statt über Namen](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md) sowie in diesem Thema.

Die DEF-Datei für eine DLL, die den Code für die Implementierung einer binären Suchstruktur enthält, könnte z. B. folgendermaßen aussehen:

```
LIBRARY   BTREE
EXPORTS
   Insert   @1
   Delete   @2
   Member   @3
   Min   @4
```

Bei Verwendung der [MFC DLL-Assistenten](../mfc/reference/mfc-dll-wizard.md) zum Erstellen einer MFC-DLL der Assistent eine DEF-Gerüstdatei für Sie erstellt und automatisch wieder zu Ihrem Projekt hinzugefügt. Fügen Sie die Namen der zu exportierenden Funktionen in diese Datei ein. Für MFC-fremde DLLs müssen Sie die DEF-Datei selbst erstellen und sie dem Projekt hinzufügen.

Wenn Sie Funktionen in eine C++-Datei exportieren, müssen Sie entweder die ergänzten Namen in die DEF-Datei einfügen oder die exportierten Funktionen unter Verwendung von extern "C" mit der standardmäßigen C-Bindung definieren. Wenn Sie die ergänzten Namen in der DEF-Datei angeben müssen, können Sie sie abrufen, indem Sie mit der [DUMPBIN](../build/reference/dumpbin-reference.md) tool oder mit der Linker [/MAP](../build/reference/map-generate-mapfile.md) Option. Beachten Sie, dass die vom Compiler erzeugten, ergänzten Namen compilerspezifisch sind. Wenn Sie die vom Visual C++-Compiler erzeugten, ergänzten Namen in eine DEF-Datei einfügen, ist es erforderlich, dass Anwendungen, die mit der DLL verknüpft werden, mit derselben Version von Visual C++ erstellt wurden. Auf diese Weise ist gewährleistet, dass die ergänzten Namen in der aufrufenden Anwendung mit den exportierten Namen in der DEF-Datei der DLL übereinstimmen.

Wenn Sie erstellen eine [Erweiterungs-DLL](../build/extension-dlls-overview.md), und Exportieren mit einer DEF-Datei, platzieren Sie den folgenden Code am Anfang und Ende der Headerdateien ein, die die exportierten Klassen enthalten:

```
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

Diese Zeilen stellen Sie sicher, dass MFC-Variablen, die intern verwendet oder hinzugefügt werden, Ihre Klassen, werden exportiert (oder nicht importiert), von der MFC-Erweiterungs-DLL. Wenn Sie z. B. eine Klasse mithilfe von `DECLARE_DYNAMIC` ableiten, wird das Makro erweitert und Ihrer Klasse wird eine Membervariable `CRuntimeClass` hinzugefügt. Ohne diese vier Zeilen wird die DLL u. U. nicht einwandfrei kompiliert bzw. verknüpft, oder es tritt ein Fehler auf, wenn die Clientanwendung mit der DLL verknüpft wird.

Der Linker verwendet beim Erstellen der DLL die DEF-Datei, um eine Exportdatei (.exp) und eine Importbibliothek (.lib) zu erstellen. Anschließend verwendet der Linker die Exportdatei zum Erstellen der DLL-Datei. Ausführbare, implizit mit der DLL verknüpfte Dateien werden bei ihrer Erstellung mit der Importbibliothek verknüpft.

Beachten Sie, dass MFC selbst die DEF-Dateien verwendet, um Funktionen und Klassen aus MFCx0.dll zu exportieren.

## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Exportieren Sie aus einer DLL mithilfe von __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)

- [Exportieren Sie und importieren Sie mithilfe von AFX_EXT_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)

- [Exportieren von C++-Funktionen für die Verwendung in ausführbaren c-Dateien](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Exportieren von C-Funktionen für die Verwendung in ausführbaren C oder C++-Dateien](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Bestimmen Sie die Exportmethode verwendet werden](../build/determining-which-exporting-method-to-use.md)

- [Importieren Sie in eine Anwendung mithilfe von "__declspec(dllimport)" "](../build/importing-into-an-application-using-declspec-dllimport.md)

- [Initialisieren einer DLL](../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [DEF-Dateien](../build/reference/module-definition-dot-def-files.md)

- [Regeln für moduldefinitionsanweisungen](../build/reference/rules-for-module-definition-statements.md)

- [Ergänzte Namen](../build/reference/decorated-names.md)

- [Importieren und Exportieren von Inlinefunktionen](../build/importing-and-exporting-inline-functions.md)

- [Gegenseitige Importe](../build/mutual-imports.md)

## <a name="see-also"></a>Siehe auch

[Exportieren aus einer DLL](../build/exporting-from-a-dll.md)