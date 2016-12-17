---
title: "Schwerwiegender Fehler C1081"
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
  - "C1081"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1081"
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1081
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Symbol': Dateiname zu lang  
  
 Die Länge eines Dateipfadnamens überschreitet `_MAX_PATH` \(gemäß **STDLIB.h** mit 260 Zeichen definiert\).  Kürzen Sie den Dateinamen.  
  
 Beim Aufruf von **CL.exe** mit einem kurzen Dateinamen muss der Compiler u. U. einen vollständigen Pfadnamen generieren.  Durch `cl -c myfile.cpp` kann z. B. folgende Compilerausgabe generiert werden:  
  
```  
D:\<very-long-directory-path>\myfile.cpp  
```