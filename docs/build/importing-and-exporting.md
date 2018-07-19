---
title: Importieren und Exportieren von | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], importing
- exporting DLLs [C++]
- importing DLLs [C++]
- DLLs [C++], exporting from
- __declspec(dllimport) keyword [C++]
ms.assetid: 7c44c2aa-2117-4cec-9615-a65bfd3f8f7b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ee3ffe33dbb99f1f9b4124e2695d2e56dbe5544
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368872"
---
# <a name="importing-and-exporting"></a>Importieren und Exportieren
Sie können Öffentliche Symbole in eine Anwendung importieren oder Exportieren von Funktionen aus einer DLL mithilfe von zwei Methoden:  
  
-   Verwenden Sie eine Moduldefinitionsdatei (.def) beim Erstellen der DLL  
  
-   Verwenden Sie die Schlüsselwörter **von "__declspec(dllimport)" "** oder **__declspec(dllexport)** in einer Funktionsdefinition in die Hauptassembly der Anwendung  
  
## <a name="using-a-def-file"></a>Mithilfe einer DEF-Datei  
 Eine Moduldefinitionsdatei (.def) ist eine Textdatei mit einer oder mehreren Modulanweisungen, die verschiedene Attribute einer DLL beschreiben. Wenn Sie nicht verwenden **von "__declspec(dllimport)" "** oder **__declspec(dllexport)** zum Exportieren DLLs-Funktionen benötigt die DLL eine DEF-Datei.  
  
 DEF-Dateien können [importieren in eine Anwendung](../build/importing-using-def-files.md) oder [exportieren aus einer DLL](../build/exporting-from-a-dll-using-def-files.md).  
  
## <a name="using-declspec"></a>__Declspec verwenden  
 Visual C++ verwendet **von "__declspec(dllimport)" "** und **__declspec(dllexport)** zum Ersetzen der **__export** Schlüsselwort, die zuvor in 16-Bit-Versionen von Visual C++ verwendet.  
  
 Sie müssen nicht mit **von "__declspec(dllimport)" "** für Ihren Code ordnungsgemäß kompiliert, aber auf diese Weise kann der Compiler besseren Code zu generieren. Der Compiler kann besseren Code zu generieren, da bestimmt werden kann, ob eine Funktion in einer DLL, vorhanden ist oder nicht dem kann der Compiler Code zu erzeugen, die eine Dereferenzierungsebene überspringt, die normalerweise in einem Funktionsaufruf vorhanden wäre, die eine DLL-Grenze überschritten. Sie müssen allerdings verwenden **von "__declspec(dllimport)" "** Variablen verwendet, die in einer DLL zu importieren.  
  
 Mit dem richtigen DEF-Datei EXPORTS-Abschnitt **__declspec(dllexport)** ist nicht erforderlich. **__declspec(dllexport)** wurde hinzugefügt, um eine einfache Möglichkeit zum Exportieren von Funktionen aus einer .exe oder .dll-Datei ohne Verwendung einer DEF-Datei bereitzustellen.  
  
 Die Portable Win32-Anwendung ist so konzipiert, dass die Anzahl der Seiten zu minimieren, die abgefragt werden müssen, um Importe zu beheben. Zu diesem Zweck werden die Importadressen für ein Programm an einem Ort die importieren Local Address Table aufgerufen. Dadurch wird das Ladeprogramm höchstens zwei Seiten zu ändern, wenn diese Importe zugreift.  
  
## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?  
  
-   [Importieren in eine Anwendung](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Exportieren aus einer DLL](../build/exporting-from-a-dll.md)  
  
## <a name="see-also"></a>Siehe auch  
 [DLLs in Visual C++](../build/dlls-in-visual-cpp.md)