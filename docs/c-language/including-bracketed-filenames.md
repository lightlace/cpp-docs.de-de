---
title: "Einschließlich Dateinamen in Klammern | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 6a4e5411-c35e-48b8-90ef-b37ac324ed94
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f118417a7ed2fdf8cad77775e144b81655c56916
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="including-bracketed-filenames"></a>Einschließlich Dateinamen in Klammern
**ANSI 3.8.2** Die Methode zum Suchen von Quelldateien, die einbezogen werden können  
  
 Der Präprozessor sucht nicht in Verzeichnissen der übergeordneten Dateien nach Dateispezifikationen, die in eckige Klammern eingeschlossen werden. Eine „übergeordnete“ Datei ist die Datei, die die [#include](../preprocessor/hash-include-directive-c-cpp.md)-Anweisung enthält. Stattdessen beginnt die Suche nach der Datei in den Verzeichnissen, die in der Compilerbefehlszeile nach "/I" angegeben werden. Wenn die /I-Option nicht vorhanden ist oder Fehler auftreten, verwendet der Präprozessor die INCLUDE-Umgebungsvariable, um alle Includedateien in spitzen Klammern zu suchen. Die INCLUDE-Umgebungsvariable kann mehrere Pfade enthalten, die durch Semikolons (**;**) voneinander getrennt sind. Wenn mehrere Verzeichnisse in der /I-Option oder der INCLUDE-Umgebungsvariablen enthalten sind, werden diese vom Präprozessor in der Reihenfolge durchsucht, in der sie angezeigt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Präprozessoranweisungen](../c-language/preprocessing-directives.md)