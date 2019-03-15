---
title: Importieren und Exportieren
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], importing
- exporting DLLs [C++]
- importing DLLs [C++]
- DLLs [C++], exporting from
- __declspec(dllimport) keyword [C++]
ms.assetid: 7c44c2aa-2117-4cec-9615-a65bfd3f8f7b
ms.openlocfilehash: 882010cd28c291e9f49ca0f7dd9d646c70130184
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57815826"
---
# <a name="importing-and-exporting"></a>Importieren und Exportieren

Sie können Öffentliche Symbole in eine Anwendung importieren oder Exportieren von Funktionen aus einer DLL mithilfe von zwei Methoden:

- Verwenden Sie eine Moduldefinitionsdatei (.def) beim Erstellen der DLL

- Verwenden Sie die Schlüsselwörter **von "__declspec(dllimport)" "** oder **__declspec(dllexport)** in einer Funktionsdefinition in der hauptanwendung

## <a name="using-a-def-file"></a>Dien .def-Datei

Eine Moduldefinitionsdatei (.def) ist eine Textdatei mit einer oder mehreren Modulanweisungen, die verschiedene Attribute einer DLL beschreiben. Wenn Sie nicht verwenden **von "__declspec(dllimport)" "** oder **__declspec(dllexport)** zum Exportieren DLLs-Funktionen benötigt die DLL eine DEF-Datei.

DEF-Dateien können [importieren in eine Anwendung](importing-using-def-files.md) oder [exportieren aus einer DLL](exporting-from-a-dll-using-def-files.md).

## <a name="using-declspec"></a>__Declspec verwenden

Visual C++ verwendet **von "__declspec(dllimport)" "** und **__declspec(dllexport)** ersetzen die **__export** Schlüsselwort, das zuvor in 16-Bit-Versionen von Visual C++.

Sie müssen nicht mit **von "__declspec(dllimport)" "** für Ihren Code ordnungsgemäß kompiliert, aber auf diese Weise können Sie den Compiler, besseren Code zu generieren. Der Compiler kann besseren Code zu generieren, da sie bestimmen kann, ob eine Funktion in einer DLL oder nicht vorhanden, sodass den Compiler Code erstellt, die eine Dereferenzierungsebene überspringt, die normalerweise in einem Funktionsaufruf vorhanden wäre, die eine DLL-Grenze überschritten. Sie müssen allerdings verwenden **von "__declspec(dllimport)" "** Variablen verwendet, die in einer DLL zu importieren.

Mit dem richtigen DEF-Datei EXPORTS-Abschnitt **__declspec(dllexport)** ist nicht erforderlich. **__declspec(dllexport)** bieten eine einfache Möglichkeit zum Exportieren von Funktionen aus einer .exe oder .dll-Datei, ohne über eine DEF-Datei hinzugefügt wurde.

Das Format Portable Win32-Anwendung soll die Anzahl der Seiten zu minimieren, die abgefragt werden müssen, um Importe zu beheben. Zu diesem Zweck werden die Importadressen für ein Programm in einem zentralen Ort, dem Namen der Tabelle importieren. Dadurch wird nur ein oder zwei Seiten zu ändern, wenn diese Importe stellen Zugriff auf das Ladeprogramm.

## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Importieren in eine Anwendung](importing-into-an-application-using-declspec-dllimport.md)

- [Exportieren aus einer DLL](exporting-from-a-dll.md)

## <a name="see-also"></a>Siehe auch

[DLLs in Visual C++](dlls-in-visual-cpp.md)
