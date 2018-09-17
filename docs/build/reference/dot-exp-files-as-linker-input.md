---
title: . EXP-Dateien als Linkereingabe | Microsoft-Dokumentation
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
ms.openlocfilehash: 4badc93f38d5ce76dcc294ad4ae216c8e3f6454c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45724008"
---
# <a name="exp-files-as-linker-input"></a>.EXP-Dateien als Eingabe für den Linker

Exportdateien (.exp) enthalten Informationen zu den exportierten Funktionen und Daten-Elementen. Wenn LIB eine Importbibliothek erstellt wird, wird auch eine .exp-Datei. Verwenden Sie die EXP-Datei, wenn Sie ein Programm, die exportiert verknüpfen in und aus einem anderen Programm importiert wird, entweder direkt oder indirekt. Wenn Sie eine mit einer EXP-Datei Verknüpfung, ergibt LINK keine Importbibliothek, da es wird davon ausgegangen, dass LIB noch nicht erstellt. Details zu .exp-Dateien und Importbibliotheken, finden Sie unter [arbeiten mit Importbibliotheken und Exportdateien](../../build/reference/working-with-import-libraries-and-export-files.md).

## <a name="see-also"></a>Siehe auch

[LINK-Eingabedateien](../../build/reference/link-input-files.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)