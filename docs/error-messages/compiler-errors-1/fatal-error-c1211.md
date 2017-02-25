---
title: "Schwerwiegender Fehler C1211 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1211"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1211"
ms.assetid: df0ca70d-ec6e-4400-926a-b877e2599978
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Schwerwiegender Fehler C1211
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das benutzerdefinierte TypeForwardedTo\-Attribut wird von der installierten Laufzeitversion nicht unterstützt.  
  
 C1211 tritt auf, wenn Sie einen Compiler der aktuellen Version, aber eine Common Language Runtime \(CLR\) einer früheren Version verwenden.  
  
 Bestimmte Funktionen des Compilers funktionieren möglicherweise nicht in einer früheren Version der Laufzeit.  
  
 Installieren Sie die CLR, die im Lieferumfang des von Ihnen verwendeten Compilers enthalten war, um C1211 zu beheben.  
  
 Weitere Informationen finden Sie unter [Type Forwarding \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md).