---
title: "Compilerfehler C3505"
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
  - "C3505"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3505"
ms.assetid: ed73c99e-93a1-4f3a-bac7-ba7ed5d836e4
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3505
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Typbibliothek 'guid' kann nicht geladen werden  
  
 C3505 kann durch das Ausführen des \(32\-Bit zu\) 64\-Bit\-Cross\-Compilers auf einem 64\-Bit\-Computer verursacht werden, da der Compiler unter WOW64 ausgeführt wird und lediglich in der Lage ist, Daten im 32\-Bit\-Registrierungshive zu lesen.  
  
 Sie können diese Ursache für C3505 vermeiden, indem Sie 32\-Bit\- und 64\-Bit\-Versionen der Typbibliothek erstellen, die Sie importieren möchten, und beide Versionen registrieren.  Sie können auch einen systemeigenen 64\-Bit\-Compiler verwenden, jedoch müssen in diesem Fall die VC\+\+\-Verzeichnisse in der IDE geändert werden, sodass diese auf den 64\-Bit\-Compiler zeigen.  
  
 Weitere Informationen finden Sie unter  
  
-   [Gewusst wie: Aktivieren eines 64\-Bit\-Visual C\+\+\-Toolsets auf der Befehlszeile](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)  
  
-   [Gewusst wie: Aktivieren eines 64\-Bit\-Visual C\+\+\-Toolsets auf der Befehlszeile](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)  
  
-   [Gewusst wie: Konfigurieren von Visual C\+\+\-Projekten für 64\-Bit\-Zielplattformen](../../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)