---
title: . EXP-Dateien als Linkereingabe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f9b5c118e81372bd57810a9472526909ed21f765
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371098"
---
# <a name="exp-files-as-linker-input"></a>.EXP-Dateien als Eingabe für den Linker
Exportdateien (.exp) enthalten Informationen über exportierte Funktionen und Daten enthaltenen Elemente. Beim Erstellen eine Importbibliothek LIB erstellt wird auch eine .exp-Datei erstellt. Wenn Sie ein Programm, die verknüpfen sowohl in exportiert und aus einem anderen Programm importiert wird, entweder direkt oder indirekt, verwenden Sie die Exportdatei an. Wenn Sie eine .exp-Datei verknüpfen, wird LINK keine Importbibliothek erzeugt, da davon ausgegangen wird, dass LIB noch nicht erstellt. Ausführliche Informationen zu .exp-Dateien und Importbibliotheken finden Sie unter [arbeiten mit Importbibliotheken und Exportdateien](../../build/reference/working-with-import-libraries-and-export-files.md).  
  
## <a name="see-also"></a>Siehe auch  
 [LINK-Eingabedateien](../../build/reference/link-input-files.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)