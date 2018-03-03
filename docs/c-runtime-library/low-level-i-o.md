---
title: E/A auf niedriger Ebene | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.io
dev_langs:
- C++
helpviewer_keywords:
- I/O [CRT], low-level
- I/O [CRT], functions
- low-level I/O routines
- file handles [C++]
- file handles [C++], I/O functions
ms.assetid: 53e11bdd-6720-481c-8b2b-3a3a569ed534
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cc923e8c638f51720aaffbb8c26aaa65bb230731
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="low-level-io"></a>E/A auf niedriger Ebene
Diese Funktionen rufen direkt das Betriebssystem für einen Vorgang auf, der sich auf einer niedrigeren Ebene befindet als der durch Stream-E/A bereitgestellte Vorgang. Eingabe- und Ausgabeaufrufe auf niedriger Ebene puffern oder formatieren keine Daten.  
  
 Routinen auf niedriger Ebene können mit den folgenden vordefinierten Dateideskriptoren auf Standardstreams zugreifen, die beim Programmstart geöffnet werden.  
  
|Stream|Dateideskriptor|  
|------------|---------------------|  
|`stdin`|0|  
|`stdout`|1|  
|`stderr`|2|  
  
 E/A-Routinen auf niedriger Ebene legen die globale Variable [errno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) fest, wenn ein Fehler auftritt. Sie müssen nur dann STDIO.H bei der Verwendung von Funktionen auf niedriger Ebene einschließen, wenn das Programm eine in STDIO.H definierte Konstante erfordert, z.B. den Indikator für das Dateiende (`EOF`).  
  
### <a name="low-level-io-functions"></a>E/A-Funktionen auf niedriger Ebene  
  
|Funktion|Mit|  
|--------------|---------|  
|[_close](../c-runtime-library/reference/close.md)|Datei schließen|  
|[_commit](../c-runtime-library/reference/commit.md)|Datei auf Datenträger leeren|  
|[_creat, _wcreat](../c-runtime-library/reference/creat-wcreat.md)|Datei erstellen|  
|[_dup](../c-runtime-library/reference/dup-dup2.md)|Nächsten verfügbaren Dateideskriptor für eine angegebene Datei zurückgeben|  
|[_dup2](../c-runtime-library/reference/dup-dup2.md)|Zweiten Deskriptor erstellen, für die angegebenen Datei erstellen|  
|[_eof](../c-runtime-library/reference/eof.md)|Dateiende prüfen|  
|[_lseek, _lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)|Position des Dateizeigers auf einen angegebenen Speicherort ändern|  
|[_open, _wopen](../c-runtime-library/reference/open-wopen.md)|Datei öffnen|  
|[_read](../c-runtime-library/reference/read.md)|Daten von Datei lesen|  
|[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md), [_sopen_s, _wsopen_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|Datei für die Dateifreigabe öffnen|  
|[_tell, _telli64](../c-runtime-library/reference/tell-telli64.md)|Aktuelle Dateizeigerposition abrufen|  
|[_umask](../c-runtime-library/reference/umask.md), [_umask_s](../c-runtime-library/reference/umask-s.md)|Dateiberechtigungsmaske festlegen|  
|[_write](../c-runtime-library/reference/write.md)|Daten in Datei schreiben|  
  
 `_dup` und `_dup2` werden im Allgemeinen verwendet, um verschiedenen Dateien die vordefinierten Dateideskriptoren zuzuordnen.  
  
## <a name="see-also"></a>Siehe auch  
 [Eingabe und Ausgabe](../c-runtime-library/input-and-output.md)   
 [Run-Time Routines by Category (Laufzeitroutinen nach Kategorie)](../c-runtime-library/run-time-routines-by-category.md)   
 [Systemaufrufe](../c-runtime-library/system-calls.md)