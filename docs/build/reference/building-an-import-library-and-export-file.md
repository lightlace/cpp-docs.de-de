---
title: Erstellen einer Importbibliothek und einer Exportdatei | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLibrarianTool.ModuleDefinitionFile
- VC.Project.VCLibrarianTool.ExportNamedFunctions
- VC.Project.VCLibrarianTool.GenerateDebug
- VC.Project.VCLibrarianTool.ForceSymbolReferences
dev_langs:
- C++
helpviewer_keywords:
- OUT library manager option
- INCLUDE library manager option
- /DEF library manager option
- exporting data
- import libraries, building
- -INCLUDE library manager option
- /OUT library manager option
- DEF library manager option
- -DEF library manager option
- -OUT library manager option
- /INCLUDE library manager option
- -EXPORT library manager option
- exporting data, export (.exp) files
- /EXPORT library manager option
- EXPORT library manager option
- .lib files
- EXP files
ms.assetid: 2fe4f30a-1dd6-4b05-84b5-0752e1dee354
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 75f629c8a9c8a06f02024e9d52ab13b2d12b234c
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860389"
---
# <a name="building-an-import-library-and-export-file"></a>Erstellen einer Importbibliothek und einer Exportdatei

Zum Erstellen einer Importbibliothek und -Datei exportieren, verwenden Sie die folgende Syntax:

> **LIB/DEF**[**:**<em>Definitionsdatei (deffile)</em>] [*Optionen*] [*Objektdateien*] [*Bibliotheken*]

Wenn/DEF angegeben wird, erstellt LIB die Ausgabedateien von Exportspezifikationen, die in der LIB-Befehl übergeben werden. Es gibt drei Methoden zum Angeben von Exports, aufgelistet in empfohlener Reihenfolge von Nutzen:

1. Ein **__declspec(dllexport)** Definition eines der *Objektdateien* oder *Bibliotheken*

1. Eine Spezifikation von/Export:*Namen* in der LIB-Befehlszeile

1. Eine Definition in einem **EXPORTE** -Anweisung in einem *Definitionsdatei (deffile)*

Dies sind die gleichen Methoden, die Sie zum Festlegen von Exporten, beim Verknüpfen von einem ausführenden Programm verwenden. Ein Programm kann mehr als eine Methode verwenden. Sie können Teile der LIB-Befehl angeben (z. B. mehrere *Objektdateien* oder/Export-Spezifikationen) können Sie in einer Befehlsdatei in der LIB-Befehl, wie Sie in einem Linkbefehl.

Die folgenden Optionen gelten für das Erstellen einer Importbibliothek und -Datei exportieren:

> **/ OUT:** *importieren*

Überschreibt den Standardnamen der Ausgabe für die *importieren* Bibliothek erstellt wird. Wenn/Out nicht angegeben ist, wird der Standardname ist der Basisname der ersten Objektdatei oder -Bibliothek in der LIB-Befehl und die Erweiterung. Lib. Die Exportdatei erhält den gleichen Basisnamen wie die Importbibliothek und die Erweiterung. "exp".

> **/ EXPORT:** *Eintragsname* \[ **=** *Internalname*]\[,**\@** <em>ordinal</em>\[, **NONAME**]]\[, **Daten**]

Exportiert eine Funktion von Ihrem Programm aus, um andere Programme, um die Funktion zu ermöglichen. Sie können auch Daten exportieren (mithilfe der **Daten** Schlüsselwort). Exporte werden in der Regel in eine DLL-Datei definiert.

Die *Eintragsname* ist der Name der Funktion oder des Elements, wie die vom aufrufenden Programm verwendet werden. Optional können Sie angeben der *Internalname* wie die Funktion bezeichnet, im Programm definiert; in der Standardeinstellung *Internalname* ist identisch mit *Eintragsname*. Die *ordinal* gibt Sie einen Index in die Tabelle "Exportieren" im Bereich von 1 bis 65.535 sein, wenn Sie keinen angeben *ordinal*, LIB weist ein. Die **NONAME** Schlüsselwort exportiert die Funktion nur als Ordnungszahl, ohne eine *Eintragsname*. Die **Daten** -Schlüsselwort wird verwendet, um Objekte, die nur Daten zu exportieren.

> **/ INCLUDE:** *Symbol*

Fügt das angegebene *Symbol* der Symboltabelle. Diese Option ist nützlich für das Erzwingen der Verwendung eines Bibliotheksobjekts, die andernfalls nicht einbezogen werden sollen.

Beachten Sie, dass wenn Sie die Importbibliothek in einem vorherigen Schritt erstellen, bevor Sie die DLL-Datei erstellen, den gleichen Satz von Objektdateien müssen beim Erstellen der DLL-Datei übergeben werden wie bei der Erstellung der Importbibliothek.

## <a name="see-also"></a>Siehe auch

[Arbeiten mit Importbibliotheken und Exportdateien](../../build/reference/working-with-import-libraries-and-export-files.md)
