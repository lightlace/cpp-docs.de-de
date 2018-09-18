---
title: BSCMAKE-Fehler BK1503 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1503
dev_langs:
- C++
helpviewer_keywords:
- BK1503
ms.assetid: e6582344-b91e-486f-baf3-4f9028d83c3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 16bf228804cb24f4fe7a2428dc581116d4cec91d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064663"
---
# <a name="bscmake-error-bk1503"></a>BSCMAKE-Fehler BK1503

Datei "Dateiname" kann nicht geschrieben werden. [: Grund]

BSCMAKE kombiniert die SBR-Dateien, die während der Kompilierung in einer Browserdatenbank generiert. Wenn die resultierende Browserdatenbank 64 MB übersteigt oder die Anzahl der Eingabedateien (.sbr) 4.092 überschreitet, wird dieser Fehler ausgegeben werden.

Wenn das Problem durch mehr als 4.092 SBR-Dateien verursacht wird, müssen Sie die Anzahl der Eingabedateien reduzieren. Von in Visual Studio, dies kann erreicht werden durch [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) Ihr gesamtes Projekt, und klicken Sie auf erneute zugriffsprüfung während pro Datei.

Wenn das Problem durch eine BSC-Datei, die größer als 64 MB verursacht wird, wird verringert die Anzahl der SBR-Dateien als Eingabe die resultierende BSC-Datei zu verkleinern. Darüber hinaus kann die Menge von Browserinformationen durch die Verwendung der/em (ausschließen Makro erweiterte Symbole), El (lokale Variablen ausschließen) und/es einsetzen (Ausschließen von Systemdateien) reduziert werden.

## <a name="see-also"></a>Siehe auch

[BSCMAKE-Optionen](../../build/reference/bscmake-options.md)