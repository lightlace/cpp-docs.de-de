---
title: Linkertoolfehler Lnk1181 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1181
dev_langs:
- C++
helpviewer_keywords:
- LNK1181
ms.assetid: 984b0db6-e331-4284-b2a7-a212fe96c486
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 617678e5453acdafaf72875857b0e0f9b84a110a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33301358"
---
# <a name="linker-tools-error-lnk1181"></a>Linkertoolfehler LNK1181
Eingabedatei 'Dateiname' kann nicht geöffnet werden.  
  
 Der Linker konnte nicht gefunden. `filename` , da er nicht vorhanden, oder der Pfad wurde nicht gefunden.  
  
 Einige häufige Ursachen für Fehler LNK1181 gehören:  
  
-   `filename` verwiesen wird, als zusätzliche Abhängigkeit auf der Linkerzeile an, aber die Datei nicht vorhanden ist.  
  
-   Ein **/LIBPATH** -Anweisung, die das Verzeichnis mit gibt `filename` ist nicht vorhanden.  
  
 Um die oben genannten Probleme zu beheben, stellen Sie sicher, dass alle Dateien in der Linkerzeile verwiesen auf dem System vorhanden sind.  Stellen Sie außerdem sicher, es ist ein **/LIBPATH** -Anweisung für jedes Verzeichnis, eine Linker abhängige Datei enthält.  
  
 Eine weitere mögliche Ursache für LNK1181 ist, dass ein langer Dateiname mit eingebetteten Leerzeichen nicht in Anführungszeichen eingeschlossen wurde.  In diesem Fall der Linker erkennt nur einen Dateinamen bis zum ersten Leerzeichen und dann angenommen Dateierweiterung. Objekt  Die Lösung für dieses Problem besteht darin, schließen Sie den langen Dateinamen (Name, Pfad und Dateiname) in Anführungszeichen ein.  
  
 Weitere Informationen finden Sie unter [LIB-Dateien als Linkereingabe](../../build/reference/dot-lib-files-as-linker-input.md).  
  
## <a name="see-also"></a>Siehe auch  
 [/LIBPATH (Zusätzlicher Libpath-Pfad)](../../build/reference/libpath-additional-libpath.md)