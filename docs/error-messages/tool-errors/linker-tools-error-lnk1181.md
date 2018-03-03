---
title: Linkertoolfehler Lnk1181 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1181
dev_langs:
- C++
helpviewer_keywords:
- LNK1181
ms.assetid: 984b0db6-e331-4284-b2a7-a212fe96c486
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8f5092d4f3ce7b4f96ca4dc5c1554483a7fc3a0b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1181"></a>Linkertoolfehler LNK1181
Eingabedatei 'Dateiname' kann nicht geöffnet werden.  
  
 Der Linker konnte nicht gefunden. `filename` , da er nicht vorhanden, oder der Pfad wurde nicht gefunden.  
  
 Einige häufige Ursachen für Fehler LNK1181 gehören:  
  
-   `filename`verwiesen wird, als zusätzliche Abhängigkeit auf der Linkerzeile an, aber die Datei nicht vorhanden ist.  
  
-   Ein **/LIBPATH** -Anweisung, die das Verzeichnis mit gibt `filename` ist nicht vorhanden.  
  
 Um die oben genannten Probleme zu beheben, stellen Sie sicher, dass alle Dateien in der Linkerzeile verwiesen auf dem System vorhanden sind.  Stellen Sie außerdem sicher, es ist ein **/LIBPATH** -Anweisung für jedes Verzeichnis, eine Linker abhängige Datei enthält.  
  
 Eine weitere mögliche Ursache für LNK1181 ist, dass ein langer Dateiname mit eingebetteten Leerzeichen nicht in Anführungszeichen eingeschlossen wurde.  In diesem Fall der Linker erkennt nur einen Dateinamen bis zum ersten Leerzeichen und dann angenommen Dateierweiterung. Objekt  Die Lösung für dieses Problem besteht darin, schließen Sie den langen Dateinamen (Name, Pfad und Dateiname) in Anführungszeichen ein.  
  
 Weitere Informationen finden Sie unter [LIB-Dateien als Linkereingabe](../../build/reference/dot-lib-files-as-linker-input.md).  
  
## <a name="see-also"></a>Siehe auch  
 [/ LIBPATH (Libpath-Pfad)](../../build/reference/libpath-additional-libpath.md)