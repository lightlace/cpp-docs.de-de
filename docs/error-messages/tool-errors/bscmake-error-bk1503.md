---
title: "BSCMAKE-Fehler BK1503"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "BK1503"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1503"
ms.assetid: e6582344-b91e-486f-baf3-4f9028d83c3b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# BSCMAKE-Fehler BK1503
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Schreiben in Datei "Dateiname" nicht möglich \[: Grund\]  
  
 BSCMAKE kombiniert die während der Kompilierung generierten SBR\-Dateien in eine Browserdatenbank.  Dieser Fehler wird ausgegeben, wenn die Browserdatenbank 64 MB überschreitet oder wenn die Anzahl der Eingabedateien \(SBR\-Dateien\) 4.092 überschreitet.  
  
 Wenn das Problem durch mehr als 4.092 SBR\-Dateien verursacht wird, muss die Anzahl der Eingabedateien reduziert werden.  Innerhalb von Visual Studio ist dies mit [\/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) für ein gesamtes Projekt möglich; anschließend sollte jede Datei einzeln neu überprüft werden.  
  
 Wenn das Problem durch eine BSC\-Datei größer als 64 MB verursacht wird, reduziert eine Verringerung der Anzahl von SBR\-Dateien als Eingabe die Größe der resultierenden BSC\-Datei.  Zusätzlich kann die Menge an Browseinformationen durch die Verwendung von **\/Em** \(durch Makros expandierte Symbole ausschließen\), **\/El** \(lokale Variablen ausschließen\) und **\/Es** \(Systemdateien ausschließen\) reduziert werden.  
  
## Siehe auch  
 [BSCMAKE\-Optionen](../../build/reference/bscmake-options.md)