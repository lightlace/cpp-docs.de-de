---
title: "Erstellen einer Importbibliothek und einer Exportdatei | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLibrarianTool.ModuleDefinitionFile"
  - "VC.Project.VCLibrarianTool.ExportNamedFunctions"
  - "VC.Project.VCLibrarianTool.GenerateDebug"
  - "VC.Project.VCLibrarianTool.ForceSymbolReferences"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".lib-Dateien"
  - "/DEF (Bibliotheks-Manager-Option)"
  - "/EXPORT (Bibliotheks-Manager-Option)"
  - "/INCLUDE (Bibliotheks-Manager-Option)"
  - "/OUT (Bibliotheks-Manager-Option)"
  - "DEF (Bibliotheks-Manager-Option)"
  - "-DEF (Bibliotheks-Manager-Option)"
  - "EXP-Dateien"
  - "EXPORT (Bibliotheks-Manager-Option)"
  - "-EXPORT (Bibliotheks-Manager-Option)"
  - "Exportieren von Daten"
  - "Exportieren von Daten, Exportdateien (.exp)"
  - "Importbibliotheken, Erstellen"
  - "INCLUDE (Bibliotheks-Manager-Option)"
  - "-INCLUDE (Bibliotheks-Manager-Option)"
  - "OUT (Bibliotheks-Manager-Option)"
  - "-OUT (Bibliotheks-Manager-Option)"
ms.assetid: 2fe4f30a-1dd6-4b05-84b5-0752e1dee354
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erstellen einer Importbibliothek und einer Exportdatei
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Um eine Importbibliothek und eine Exportdatei zu erstellen, verwenden Sie die folgende Syntax:  
  
```  
LIB /DEF[:deffile] [options] [objfiles] [libraries]  
```  
  
 Wenn **\/DEF** angegeben wird, erstellt LIB die Ausgabedateien aus den Exportangaben, die im LIB\-Befehl übergeben werden.  Um Exporte anzugeben, stehen Ihnen die folgenden drei Methoden zur Verfügung. Es wird empfohlen, sie in der angegebenen Reihenfolge zu verwenden:  
  
1.  Eine **\_\_declspec\(dllexport\)**\-Definition in einer der Objektdateien \(*objfiles*\) oder Bibliotheken \(*libraries*\)  
  
2.  Die Angabe von **\/EXPORT**:*name* in der LIB\-Befehlszeile  
  
3.  Eine Definition über eine **EXPORTS**\-Anweisung in einer Definitionsdatei \(`deffile`\)  
  
 Hierbei handelt es sich um dieselben Methoden, die Sie zum Festlegen von Exporten beim Binden eines exportierenden Programms verwenden.  Ein Programm kann mehrere Methoden verwenden.  Sie können genauso wie in einem **LINK**\-Befehl einzelne Teile des LIB\-Befehls in einer Befehlsdatei angeben \(beispielsweise mehrere Objektdateien oder **\/EXPORT**\-Angaben\).  
  
 Die folgenden Optionen beziehen sich auf das Erstellen einer Importbibliothek und einer Exportdatei:  
  
 **\/OUT**:*import*  
 Überschreibt den Standardnamen für die Ausgabedatei der zu erstellenden Importbibliothek.  Wenn **\/OUT** nicht angegeben ist, wird der Standardname aus dem Basisnamen der ersten Objektdatei oder Bibliothek im LIB\-Befehl und der Erweiterung LIB zusammengesetzt.  Die Exportdatei erhält denselben Basisnamen wie die Importbibliothek sowie die Erweiterung "**.exp**".  
  
 **\/EXPORT**:*entryname*\[\=*internalname*\]\[,@`ordinal`\[,**NONAME**\]\]\[,**DATA**\]  
 Exportiert eine Funktion aus Ihrem Programm, um anderen Programmen den Aufruf dieser Funktion zu ermöglichen.  Sie können auch Daten exportieren \(mit dem **DATA**\-Schlüsselwort\).  Exporte werden gewöhnlich in einer DLL definiert.  
  
 *entryname* entspricht dem Namen der Funktion oder des Datenelements, der vom aufrufenden Programm verwendet werden muss.  Wahlweise können Sie auch den internen Namen \(*internalname*\) angeben, unter dem die Funktion im definierenden Programm verwendet wird, *internalname* und *entryname* sind standardmäßig identisch.  Der Parameter `ordinal` gibt in der Exporttabelle einen Index im Bereich von 1 bis 65.535 an. Wenn Sie keinen Wert für `ordinal` angeben, weist LIB einen Indexwert zu.  Durch das **NONAME**\-Schlüsselwort wird die Funktion ohne *entryname* nur als Ordnungszahl exportiert.  Das **DATA**\-Schlüsselwort wird für den Export von Objekten verwendet, die nur Daten enthalten.  
  
 **\/INCLUDE**:`symbol`  
 Fügt der Symboltabelle das angegebene Symbol hinzu.  Mit dieser Option kann die Verwendung eines Bibliotheksobjekts, das andernfalls nicht einbezogen würde, erzwungen werden.  
  
 Wenn Sie die Importbibliothek in einem vorherigen Schritt erstellen, muss vor der Erstellung der DLL derselbe Satz von Objektdateien zur Erstellung der DLL übergeben werden wie bei der Erstellung der Importbibliothek.  
  
## Siehe auch  
 [Arbeiten mit Importbibliotheken und Exportdateien](../../build/reference/working-with-import-libraries-and-export-files.md)