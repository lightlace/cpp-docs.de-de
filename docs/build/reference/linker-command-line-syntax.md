---
title: "Syntax f&#252;r die Linkerbefehlszeile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LINK-Tool [C++], Befehlszeilensyntax"
  - "Linker [C++], Syntax"
  - "Linkerbefehlszeile [C++]"
ms.assetid: e2a31e17-77bd-4e74-9305-75b105b26539
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Syntax f&#252;r die Linkerbefehlszeile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Um LINK.EXE auszuführen, verwenden Sie die folgende Befehlssyntax:  
  
```  
LINK arguments  
```  
  
 Die `arguments` bestehen aus Optionen und Dateinamen und können in beliebiger Reihenfolge angegeben werden.  Optionen werden zuerst verarbeitet, dann Dateien.  Argumente können mit einem oder mehreren Leerzeichen oder Tabulatorzeichen voneinander getrennt werden.  
  
> [!NOTE]
>  Sie können dieses Tool nur von der [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]\-Eingabeaufforderung aus starten.  Sie können es nicht von einer Systemeingabeaufforderung oder vom Datei\-Explorer aus starten.  
  
 In der Befehlszeile besteht eine Option aus einem Optionsbezeichner – Halbgeviertstrich \(–\) oder Schrägstrich \(\/\) – und dem Namen der Option.  Optionsnamen können nicht abgekürzt werden.  Einige Optionen verfügen über Argumente, die nach einem Doppelpunkt \(:\) angegeben werden.  Innerhalb einer Optionsangabe sind keine Leerzeichen oder Tabulatorzeichen erlaubt, ausgenommen eine Zeichenfolge in Anführungszeichen in der Option \/COMMENT.  Geben Sie numerische Argumente dezimal oder in C\-Notation an.  Bei Optionsnamen und ihren aus Schlüsselwörtern oder Dateinamen bestehenden Argumenten wird die Groß\-\/Kleinschreibung nicht beachtet. Bei Bezeichnern, die als Argumente verwendet werden, wird die Groß\-\/Kleinschreibung jedoch beachtet.  
  
 Um eine Datei an den Linker zu übergeben, geben Sie den Dateinamen in der Befehlszeile nach dem **LINK**\-Befehl an.  Sie können einen absoluten oder relativen Pfad mit dem Dateinamen angeben, und Sie können Platzhalter im Dateinamen verwenden.  Wenn Sie den Punkt \(.\) und die Erweiterung des Dateinamens weglassen, nimmt der Linker .obj als Typ für die gesuchte Datei an.  **LINK** versucht nicht, aus der Dateinamenserweiterung auf den Inhalt einer Datei zu schließen; vielmehr wird der Dateityp durch Untersuchen der Datei selbst bestimmt, und die Datei dann entsprechend verarbeitet.  
  
 Bei erfolgreicher Durchführung gibt link.exe den Wert 0 \(null\) zurück \(keine Fehler\).  Andernfalls gibt der Linker die Fehlernummer zurück, durch die die Verknüpfung gestoppt wurde.  Wenn der LNK1104 Linker generiert, gibt der Linker 1104 zurück. Entsprechend ist die niedrigste geltende Fehlernummer, die auf einen Fehler vom Linker zurückgegeben wird, 1000. Ein Rückgabewert 128 stellt ein Konfigurationsproblem entweder mit dem Betriebssystem oder einer Konfigurationsdatei dar; das Ladeprogramm hat weder link.exe oder c2.dll.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)