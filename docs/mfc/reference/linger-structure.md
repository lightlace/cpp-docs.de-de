---
title: "LINGER-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LINGER"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LINGER-Struktur"
ms.assetid: 1fb1c5bf-a64e-4a6c-89d6-1734e4fdbb1b
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# LINGER-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Struktur `LINGER` wird zum Bearbeiten der Optionen **SO\_LINGER** und **SO\_DONTLINGER** von `CAsyncSocket::GetSockOpt`.  
  
## Syntax  
  
```  
  
      struct linger {  
   u_short l_onoff;            // option on/off  
   u_short l_linger;           // linger time  
};  
```  
  
## Hinweise  
 Das Festlegen der Option **SO\_DONTLINGER** verhindert Blockieren auf Memberfunktion **Schließen** beim Warten auf die ungesendeten zu sendenden Daten.  Diese Option festzulegen ist das Festlegen von **SO\_LINGER** mit **l\_onoff**, das entsprechend auf 0 festgelegt.  
  
## Anforderungen  
 **Header:** winsock2.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CAsyncSocket::GetSockOpt](../Topic/CAsyncSocket::GetSockOpt.md)   
 [CAsyncSocket::SetSockOpt](../Topic/CAsyncSocket::SetSockOpt.md)