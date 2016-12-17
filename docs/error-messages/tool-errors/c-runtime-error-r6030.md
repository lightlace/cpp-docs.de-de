---
title: "C-Laufzeitfehler R6030"
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
  - "R6030"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6030"
ms.assetid: 0238a6c3-a033-4046-8adc-f8f99d961153
caps.latest.revision: 9
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# C-Laufzeitfehler R6030
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CRT nicht initialisiert  
  
 Dieser Fehler tritt auf, wenn Sie CRT verwenden, ohne dass der CRT\-Startcode ausgeführt wurde.  Dieser Fehler kann auftreten, wenn der Linkerschalter [\/ENTRY](../../build/reference/entry-entry-point-symbol.md) zum Überschreiben der Standardstartadresse verwendet wird. Gewöhnlich sind dies **mainCRTStartup**, **wmainCRTStartup** für eine Konsolen\-EXE\-Datei, **WinMainCRTStartup** oder **wWinMainCRTStartup** für eine Windows\-EXE\-Datei oder **\_DllMainCRTStartup** für eine DLL\-Datei.  Die C\-Laufzeit wird nur initialisiert, wenn beim Start eine der oben genannten Funktionen aufgerufen wird.