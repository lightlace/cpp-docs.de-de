---
title: "Commit-To-Disk-Konstanten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.constants"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Commit-To-Disk-Konstanten"
ms.assetid: 0b903b23-b4fa-431e-a937-51d95f695ecf
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Commit-To-Disk-Konstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
## Syntax  
  
```  
  
#include <stdio.h>  
```  
  
## Hinweise  
 Diese Microsoft\-Besonderekonstanten geben an, ob der Puffer, der mit der geöffneten Datei zugeordnet ist, den Betriebssystempuffern oder auf dem Datenträger geleert wird.  Der Modus wird in der Zeichenfolge enthalten, die den Typ des Lese\-\/Schreibzugriff auf angibt \(**"r"**, **"w"**, **"a"**, **"r\+"**, **"w\+"**, **"a\+"**\).  
  
 Die Datenträgercommitmodi sind, wie folgt:  
  
 **c**  
 Schreibt den ungeschriebenen Inhalt des angegebenen Puffers auf den Datenträger.  Diese Datenträgercommitfunktionalität tritt nur an den expliziten Aufruf auf [fflush](../c-runtime-library/reference/fflush.md) oder die [\_flushall](../c-runtime-library/reference/flushall.md)\-Funktion auf.  Dieser Modus ist während Beschäftigen vertrauliche Daten nützlich.  Wenn das Programm beendet wird, nachdem ein Aufruf von `fflush` oder `_flushall`, Sie davon ausgehen, dass die Daten die Puffer des Betriebssystems haben.  Es sei denn, eine Datei mit der Option **k** geöffnet ist, können Ihnen möglicherweise die Daten niemals auf der Festplatte, wenn das Betriebssystem auch beendet wird.  
  
 **n**  
 Schreibt den ungeschriebenen Inhalt des angegebenen Puffers zum den Puffern des Betriebssystems.  Das Betriebssystem kann Daten zwischenspeichern und eine Zeit bestimmen, auf die Festplatte zu schreiben.  In vielen Bedingungen macht dieses Verhalten für effiziente Programmverhalten.  Wenn der Datenerhalt wichtig ist \(wie Banktransaktionen oder Flugticketinformationen\), sollten Sie die Option **k** verwenden.  **n** Der Modus ist der Standard.  
  
> [!NOTE]
>  Die **k** und **n** Optionen sind nicht Teil des ANSI\-Standards für `fopen`, jedoch Microsoft\-Erweiterungen und sollten nicht verwendet werden, wo ANSI\-Portabilität gewünscht wird.  
  
## Verwenden der Datenträgercommit\-Funktion mit vorhandenem Code  
 Standardmäßig schreiben Aufrufe von [fflush](../c-runtime-library/reference/fflush.md) oder [\_flushall](../c-runtime-library/reference/flushall.md) Bibliotheksfunktionen Daten in den Puffern, die das Betriebssystem verwaltet werden.  Das Betriebssystem die optimale Zeit, die Daten auf dem Datenträger tatsächlich zu schreiben.  Die Datenträgercommitfunktion der Laufzeitbibliothek können Sie sicherstellen, dass wichtige Daten direkt auf dem Datenträger statt auf den Puffer des Betriebssystems geschrieben werden.  Sie können diese Funktion auf einem vorhandenen Programm geben, ohne es umzuschreiben, indem Sie die Objektdateien mit COMMODE.OBJ verknüpfen.  
  
 In der resultierenden ausführbaren Datei schreiben Aufrufe `fflush` den Inhalt des Puffers direkt auf der Festplatte, und Aufrufe `_flushall` schreiben Inhalt aller Puffer dem Datenträger.  Diese beiden Features sind die einzigen wirkt sich auf COMMODE.OBJ.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Stream\-E\/A](../c-runtime-library/stream-i-o.md)   
 [\_fdopen, \_wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fopen, \_wfopen](../c-runtime-library/reference/fopen-wfopen.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)