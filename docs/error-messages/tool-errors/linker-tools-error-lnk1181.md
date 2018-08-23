---
title: Linkertoolfehler Lnk1181 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/22/2018
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
ms.openlocfilehash: 3edd2f39848ea1db054dd4ceee8abf290dde7a74
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42597661"
---
# <a name="linker-tools-error-lnk1181"></a>Linkertoolfehler LNK1181
Die Eingabedatei 'Dateiname' kann nicht geöffnet werden.  
  
 Der Linker wurde nicht gefunden. `filename` , da er nicht vorhanden oder der Pfad wurde nicht gefunden.  
  
 Einige häufige Ursachen für Fehler LNK1181 gehören:  
  
-   `filename` verwiesen wird, da eine zusätzliche Abhängigkeit von der Linker-Befehlszeile, aber die Datei nicht vorhanden ist.  
  
-   Ein **/LIBPATH** Anweisung, der angibt, das Verzeichnis mit `filename` ist nicht vorhanden.  
  
 Um die oben genannten Probleme zu beheben, stellen Sie sicher, dass alle Dateien, die in der Linkerzeile verwiesen wird, auf dem System vorhanden sind.  Stellen Sie außerdem sicher, es gibt eine **/LIBPATH** -Anweisung für jedes Verzeichnis, das eine Linker-abhängige Datei enthält. 

 Weitere Informationen finden Sie unter [LIB-Dateien als Linkereingabe](../../build/reference/dot-lib-files-as-linker-input.md).
  
 Eine weitere mögliche Ursache für LNK1181 ist, dass ein langer Dateiname mit eingebetteten Leerzeichen nicht in Anführungszeichen eingeschlossen wurde.  In diesem Fall der Linker erkennt nur einen Dateinamen bis zum ersten Leerzeichen, und dann annehmen eine Dateierweiterung aus. obj.  Die Lösung für dieses Problem besteht darin, schließen Sie den langen Dateinamen (Name, Pfad und Dateiname) in Anführungszeichen ein.  

 Beim Kompilieren mit der [/p (Vorverarbeitung in eine Datei)](../../build/reference/p-preprocess-to-a-file.md) Option kann in LNK1181 führen, da diese Option die Erstellung von OBJ-Dateien unterdrückt.
  
  
  
## <a name="see-also"></a>Siehe auch  
 [/LIBPATH (Zusätzlicher Libpath-Pfad)](../../build/reference/libpath-additional-libpath.md)