---
title: BSCMAKE-Fehler BK1503 | Microsoft Docs
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
ms.openlocfilehash: 06d4a05a8f2d04c3f8a991d4444b35295408a7b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33294793"
---
# <a name="bscmake-error-bk1503"></a>BSCMAKE-Fehler BK1503
Datei 'Dateiname' kann nicht geschrieben werden. [: Grund]  
  
 BSCMAKE kombiniert die SBR-Dateien, die während der Kompilierung in einem Browserdatenbank generiert. Wenn die resultierende Browserdatenbank 64 MB überschreitet oder die Anzahl der Eingabedateien (.sbr) 4.092 überschreitet, wird dieser Fehler ausgegeben.  
  
 Wenn das Problem durch mehr als 4.092 SBR-Dateien verursacht wird, müssen Sie die Anzahl der Eingabedateien reduzieren. Aus Visual Studio dies geschieht durch [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) Ihre Gesamtprojekt, und klicken Sie dann erneut prüfen auf Basis von Datei.  
  
 Wenn das Problem durch eine BSC-Datei, die größer als 64 MB verursacht wird, wird die Verringerung von SBR-Dateien als Eingabe die resultierende BSC-Datei zu verkleinern. Darüber hinaus kann die Browserinformationen durch die Verwendung von/em (ausschließen-Makro erweitert Symbole), El (lokale Variablen ausschließen) und/es (Systemdateien ausschließen) einsetzen reduziert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [BSCMAKE-Optionen](../../build/reference/bscmake-options.md)