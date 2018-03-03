---
title: "Syntax für die Linkerbefehlszeile | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- linker [C++], syntax
- linker command line [C++]
- LINK tool [C++], command-line syntax
ms.assetid: e2a31e17-77bd-4e74-9305-75b105b26539
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3ce42aa031b91d5a4ec21ed14ac7cb47643e1325
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-command-line-syntax"></a>Syntax für die Linkerbefehlszeile
LINK zum Ausführen. EXE-Datei, verwenden Sie die folgende Befehlssyntax:  
  
```  
LINK arguments  
```  
  
 Die `arguments` Optionen und Dateinamen enthalten und können in beliebiger Reihenfolge angegeben werden. Optionen werden zuerst verarbeitet werden, und klicken Sie dann auf Dateien. Verwenden Sie eine oder mehrere Leerzeichen bzw. Tabstopps, um Argumente zu trennen.  
  
> [!NOTE]
>  Sie können dieses Tool nur von der [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]-Eingabeaufforderung aus starten. Sie können es nicht von einer Systemeingabeaufforderung oder vom Datei-Explorer aus starten.  
  
 In der Befehlszeile eine Option besteht aus einem Optionsbezeichner, entweder einem Bindestrich (-) oder einem Schrägstrich (/), gefolgt vom Namen der Option. Optionsnamen können nicht abgekürzt werden. Einige Optionen haben ein Argument an, nach einem Doppelpunkt (:)) angegeben. Keine Leerzeichen oder Tabstopps sind innerhalb einer Optionsangabe außer innerhalb einer Zeichenfolge in Anführungszeichen in der Option/Comment zulässig. Geben Sie numerische Argumente Dezimal oder C-Notation an. Bei Optionsnamen und ihren aus Schlüsselwörtern oder Dateiname Argumenten sind nicht Groß-/Kleinschreibung beachtet, aber Bezeichner als Argumente Groß-/Kleinschreibung beachtet.  
  
 Um eine Datei an dem Linker übergeben, geben Sie den Dateinamen in der Befehlszeile nach dem LINK-Befehl. Sie können einen absoluten oder relativen Pfad angeben, mit dem Dateinamen, und können Sie Platzhalter im Dateinamen verwenden. Wenn Sie den Punkt (.) und die Erweiterung weglassen, wird links obj zum Auffinden der Datei angenommen. LINK verwendet Filename Erweiterungen oder die mangelndes keine um Annahmen zum Inhalt der Dateien zu machen; Bestimmt den Typ der Datei durch Untersuchen und verarbeitet ihn entsprechend.  
  
 Link.exe gibt 0 für Erfolg (keine Fehler) zurück.  Andernfalls wird der Linker die Fehlernummer, die den Link beendet zurückgegeben.  Wenn der Linker LNK1104 generiert, gibt der Linker beispielsweise 1104 zurück.  Entsprechend ist die niedrigste Fehlernummer, die bei einem Fehler vom Linker zurückgegeben 1000.  Ein Rückgabewert von 128 stellt ein Konfigurationsproblem mit dem Betriebssystem oder einer .config-Datei dar. das Ladeprogramm wurde nicht link.exe oder c2.dll geladen werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)