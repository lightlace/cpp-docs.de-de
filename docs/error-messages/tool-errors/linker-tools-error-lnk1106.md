---
title: "Linkertoolfehler LNK1106 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1106"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1106"
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Linkertoolfehler LNK1106
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ungültige Datei oder Datenträger voll: Positionieren auf Position nicht möglich  
  
 Das Tool konnte an der *Position* in der Speicherabbilddatei weder lesen noch schreiben.  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Der Datenträger ist voll.  
  
     Geben Sie Speicherplatz frei, und führen Sie die Verknüpfung erneut durch.  
  
2.  Es wurde versucht, die Verknüpfung über ein Netzwerk herzustellen.  
  
     Die vom Linker verwendeten Speicherabbilddateien werden von einigen Netzwerken nicht vollständig unterstützt.  Versuchen Sie, die Verknüpfung auf dem lokalen Datenträger herzustellen.  
  
3.  Fehlerhafter Block auf dem Datenträger.  
  
     Obwohl dieser Fehler vom Betriebssystem und der Datenträgerhardware erkannt werden müsste, können Sie ein Programm zur Datenträgerprüfung ausführen.  
  
4.  Kein weiterer Heap\-Speicher verfügbar.  
  
     Weitere Informationen finden Sie unter [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md).