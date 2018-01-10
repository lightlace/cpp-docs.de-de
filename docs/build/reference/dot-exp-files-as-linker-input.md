---
title: . EXP-Dateien als Linkereingabe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- exporting functions
- import libraries, linker files
- linking [C++], exports
- exporting functions, information about exported functions
- exporting data, export (.exp) files
- functions [C++], exporting
- .exp files [C++]
- EXP files
ms.assetid: 399f5636-0a4d-462e-b500-5f5b9ae5ad22
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5cd6351623b230e3be1e432bd6ee0fb760da5abd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="exp-files-as-linker-input"></a>.EXP-Dateien als Eingabe für den Linker
Exportdateien (.exp) enthalten Informationen über exportierte Funktionen und Daten enthaltenen Elemente. Beim Erstellen eine Importbibliothek LIB erstellt wird auch eine .exp-Datei erstellt. Wenn Sie ein Programm, die verknüpfen sowohl in exportiert und aus einem anderen Programm importiert wird, entweder direkt oder indirekt, verwenden Sie die Exportdatei an. Wenn Sie eine .exp-Datei verknüpfen, wird LINK keine Importbibliothek erzeugt, da davon ausgegangen wird, dass LIB noch nicht erstellt. Ausführliche Informationen zu .exp-Dateien und Importbibliotheken finden Sie unter [arbeiten mit Importbibliotheken und Exportdateien](../../build/reference/working-with-import-libraries-and-export-files.md).  
  
## <a name="see-also"></a>Siehe auch  
 [LINK-Eingabedateien](../../build/reference/link-input-files.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)