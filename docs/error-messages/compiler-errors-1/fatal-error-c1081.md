---
title: "Schwerwiegender Fehler C1081 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1081"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1081"
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Schwerwiegender Fehler C1081
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Symbol': Dateiname zu lang  
  
 Die Länge eines Dateipfadnamens überschreitet `_MAX_PATH` \(gemäß **STDLIB.h** mit 260 Zeichen definiert\).  Kürzen Sie den Dateinamen.  
  
 Beim Aufruf von **CL.exe** mit einem kurzen Dateinamen muss der Compiler u. U. einen vollständigen Pfadnamen generieren.  Durch `cl -c myfile.cpp` kann z. B. folgende Compilerausgabe generiert werden:  
  
```  
D:\<very-long-directory-path>\myfile.cpp  
```