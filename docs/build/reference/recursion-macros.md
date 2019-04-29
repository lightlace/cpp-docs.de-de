---
title: Rekursionsmakros
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, recursion macros
- recursion macros
- macros, recursion
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
ms.openlocfilehash: 064bc40906bcf3a126c225585a6df43443b5c38e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319238"
---
# <a name="recursion-macros"></a>Rekursionsmakros

Verwenden Sie Rekursionsmakros NMAKE rekursiv aufgerufen. Rekursive Sitzungen erben Befehlszeilen- und Umgebungsvariablen-Makros und Tools.ini Informationen. Sie erben nicht die Makefile-definierte Rückschlussregeln oder **. SUFFIXE** und **. WERTVOLLE** Spezifikationen. Um eine rekursive NMAKE-Sitzung Makros übergeben, legen Sie eine Umgebungsvariable mit vor dem rekursiven Aufruf, definieren Sie ein Makro im Befehl für den rekursiven Aufruf, oder definieren Sie ein Makro in Tools.ini.

|Makro|Definition|
|-----------|----------------|
|**STELLEN**|Befehl, der ursprünglich zum Aufrufen von NMAKE verwendet.<br /><br /> Das $(make)-makro gibt den vollständigen Pfad zu nmake.exe.|
|**MAKEDIR**|Aktuelle Verzeichnis beim Aufruf von NMAKE.|
|**MAKEFLAGS**|Die Optionen momentan. Verwenden Sie als `/$(MAKEFLAGS)`.  Beachten Sie, dass/f nicht enthalten ist.|

## <a name="see-also"></a>Siehe auch

[Besondere NMAKE-Makros](special-nmake-macros.md)
