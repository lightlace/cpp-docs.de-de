---
title: "SOCKADDR-Struktur"
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
  - "SOCKADDR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SOCKADDR-Struktur"
ms.assetid: df1ed66a-f4b8-43f8-8db8-8c2533d25f68
caps.latest.revision: 12
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# SOCKADDR-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `SOCKADDR`\-Struktur wird verwendet, um die Adresse eines Internetprotokolls \(IP\) für einen Computer zu speichern, der an einer Windows Socket\-Kommunikation teilnimmt.  
  
## Syntax  
  
```  
  
      struct sockaddr {  
   unsigned short sa_family;  
   char sa_data[14];  
};  
```  
  
#### Parameter  
 *sa\_family*  
 Socketadressenfamilie.  
  
 *sa\_data*  
 Maximale Größe aller verschiedenen Socketadress\-Strukturen.  
  
## Hinweise  
 Das Microsoft TCP\/IP\-Kit des Socket\-Entwicklers unterstützt nur die Internetadressendomänen.  Um Werte für jeden Teil einer Adresse zu füllen, verwenden Sie die Datenstruktur von `SOCKADDR_IN`, die speziell für dieses Adressenformat vorgesehen ist.  Die Datenstrukturen `SOCKADDR` und `SOCKADDR_IN` haben die gleiche Größe.  Sie müssen einfach nur umschalten, um zwischen den beiden Strukturtypen zu wechseln.  
  
## Anforderungen  
 **Header:** winsock2.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [SOCKADDR\_IN\-Struktur](../../mfc/reference/sockaddr-in-structure.md)   
 [CAsyncSocket::Create](../Topic/CAsyncSocket::Create.md)   
 [CSocket::Create](../Topic/CSocket::Create.md)