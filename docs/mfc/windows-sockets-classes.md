---
title: "Windows Sockets-Klassen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.classes.net"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Socketklassen"
  - "Windows-Sockets [C++], Klassen"
ms.assetid: 58b9ab8d-9e44-4db3-8265-e04e713d2e9a
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Sockets-Klassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Windows Sockets bieten eine Protokoll\-unabhängige Methode des Netzwerks, zwischen zwei Computern zu kommunizieren.  Diese Sockets können synchron \(das Programm gewartet wird, bis die Kommunikation ausgeführt\) oder asynchron sein \(das Programm wird weiterhin ausgeführt, während die die Kommunikation weitergeht\).  
  
 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)  
 Kapselt die Windows Sockets API in einem Slim Wrapper.  
  
 [CSocket](../mfc/reference/csocket-class.md)  
 Hochgradige Abstraktion wird von `CAsyncSocket` abgeleitet.  Sie funktioniert synchron.  
  
 [CSocketFile](../mfc/reference/csocketfile-class.md)  
 Stellt eine `CFile`\-Schnittstelle für einen Socket Windows bereit.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)