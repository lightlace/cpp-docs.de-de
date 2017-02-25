---
title: "NMAKE: Schwerwiegender Fehler U1095 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1095"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1095"
ms.assetid: a392582b-06db-4568-9c13-450293a4fbda
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# NMAKE: Schwerwiegender Fehler U1095
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erweiterte Befehlszeile "Befehlszeile" zu lang  
  
 Nach der Makroerweiterung hat die angegebene Befehlszeile die zulässige Befehlszeilenlänge des Betriebssystems überschritten.  
  
 Unter MS\-DOS sind bis zu 128 Zeichen in einer Befehlszeile zulässig.  
  
 Falls der Befehl für ein Programm, das keine Befehlszeileneingabe von einer Datei annehmen kann, bestimmt ist, kann der Befehl geändert und die Eingabe entweder über eine Datei auf dem Datenträger oder eine Inlinedatei bereitgestellt werden.  Von **LINK** und **LIB** werden z. B. Eingaben von einer Antwortdatei angenommen.