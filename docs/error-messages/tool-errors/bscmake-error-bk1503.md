---
title: BSCMAKE-Fehler BK1503 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: BK1503
dev_langs: C++
helpviewer_keywords: BK1503
ms.assetid: e6582344-b91e-486f-baf3-4f9028d83c3b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 86f2b6d282857409cdb1e1d49e04775e9886cde4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="bscmake-error-bk1503"></a>BSCMAKE-Fehler BK1503
Datei 'Dateiname' kann nicht geschrieben werden. [: Grund]  
  
 BSCMAKE kombiniert die SBR-Dateien, die während der Kompilierung in einem Browserdatenbank generiert. Wenn die resultierende Browserdatenbank 64 MB überschreitet oder die Anzahl der Eingabedateien (.sbr) 4.092 überschreitet, wird dieser Fehler ausgegeben.  
  
 Wenn das Problem durch mehr als 4.092 SBR-Dateien verursacht wird, müssen Sie die Anzahl der Eingabedateien reduzieren. Aus Visual Studio dies geschieht durch [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) Ihre Gesamtprojekt, und klicken Sie dann erneut prüfen auf Basis von Datei.  
  
 Wenn das Problem durch eine BSC-Datei, die größer als 64 MB verursacht wird, wird die Verringerung von SBR-Dateien als Eingabe die resultierende BSC-Datei zu verkleinern. Darüber hinaus kann die Browserinformationen durch die Verwendung von/em (ausschließen-Makro erweitert Symbole), El (lokale Variablen ausschließen) und/es (Systemdateien ausschließen) einsetzen reduziert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [BSCMAKE-Optionen](../../build/reference/bscmake-options.md)