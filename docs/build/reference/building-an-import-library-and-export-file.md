---
title: Erstellen einer Importbibliothek und einer Exportdatei | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLibrarianTool.ModuleDefinitionFile
- VC.Project.VCLibrarianTool.ExportNamedFunctions
- VC.Project.VCLibrarianTool.GenerateDebug
- VC.Project.VCLibrarianTool.ForceSymbolReferences
dev_langs: C++
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
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 979e052147f058e6c46a1c10b1dd89cfd36ee362
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="building-an-import-library-and-export-file"></a>Erstellen einer Importbibliothek und einer Exportdatei
Verwenden Sie zum Erstellen einer Importbibliothek und exportieren die Datei, die folgende Syntax:  
  
```  
LIB /DEF[:deffile] [options] [objfiles] [libraries]  
```  
  
 Wenn DEF angegeben wird, erstellt LIB die Ausgabedateien aus Export-Spezifikationen, die in der LIB-Befehl übergeben werden. Es gibt drei Methoden zum Angeben von Exports, aufgelistet in empfohlener Reihenfolge von Nutzen:  
  
1.  Ein **__declspec(dllexport)** in einem der Definition der *Objektdateien* oder *Bibliotheken*  
  
2.  Eine Angabe von/Export:*Namen* in der LIB-Befehlszeile  
  
3.  Eine Definition in einer **EXPORTE** -Anweisung in einem`deffile`  
  
 Dies sind die gleichen Methoden, die Sie zum Festlegen von Exporten beim Verknüpfen von einem ausführenden Programm verwenden. Ein Programm kann mehr als eine Methode verwendet werden. Sie können Teile der LIB-Befehl angeben (z. B. mehrere *Objektdateien* oder/Export-Spezifikationen) können Sie in eine Befehlsdatei in der LIB-Befehl, wie Sie in einem LINK-Befehl.  
  
 Die folgenden Optionen gelten für das Erstellen einer Importbibliothek und exportieren Sie die Datei:  
  
 / OUT: *importieren*  
 Überschreibt den Standardnamen für die Datei von Ausgabe für die *importieren* Bibliothek erstellt wird. Wenn/Out nicht angegeben ist, wird der Standardname lautet den Basisnamen der ersten Objektdatei oder Bibliothek in der LIB-Befehl und der Erweiterung. Lib. Die Exportdatei erhält den gleichen Basisnamen wie die Importbibliothek und die Erweiterung. exp.  
  
 / EXPORT: *Eintragsname*[= *Internalname*] [, @ `ordinal`[, **NONAME**]] [, **Daten**]  
 Exportiert eine Funktion aus Ihrem Programm auf andere Programme die Funktion aufrufen können. Sie können auch Daten exportieren (mithilfe der **Daten** Schlüsselwort). Exporte werden normalerweise in einer DLL definiert.  
  
 Die *Eintragsname* ist der Name der Funktion oder Daten, der vom aufrufenden Programm verwendet werden. Optional können Sie angeben der *Internalname* wie die Funktion bezeichnet, in der definierenden Programm; standardmäßig *Internalname* ist identisch mit *Eintragsname*. Die `ordinal` gibt einen Index in der Exporttabelle im Bereich von 1 bis 65.535 sein, wenn Sie keinen angeben `ordinal`, LIB weist ein. Die **NONAME** Schlüsselwort exportiert die Funktion nur als Ordnungszahl, ohne eine *Eintragsname*. Die **Daten** Schlüsselwort wird verwendet, um Daten nur Objekte exportieren.  
  
 / INCLUDE:`symbol`  
 Fügt das angegebene Symbol zur Symboltabelle. Diese Option ist nützlich für das Erzwingen der Verwendung eines Objekts Bibliothek, die sonst nicht enthalten.  
  
 Beachten Sie, dass wenn Sie die Importbibliothek in einem vorherigen Schritt erstellen, bevor Sie die DLL-Datei erstellen, den gleichen Satz von Objektdateien müssen beim Erstellen der DLL übergeben werden wie bei der Erstellung der Importbibliothek her.  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit Importbibliotheken und Exportdateien](../../build/reference/working-with-import-libraries-and-export-files.md)