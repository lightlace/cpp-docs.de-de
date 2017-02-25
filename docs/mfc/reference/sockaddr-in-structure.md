---
title: "SOCKADDR_IN-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SOCKADDR_IN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SOCKADDR_IN-Struktur"
ms.assetid: e8cd7c34-78bd-4e28-a990-eb3ca070b7a6
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# SOCKADDR_IN-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In der Internetadressenfamilie wird die `SOCKADDR_IN`\-Struktur von Windows Sockets verwendet, um eine lokale oder Remoteendpunktadresse festlegen, mit der ein Socket verbunden werden soll.  
  
## Syntax  
  
```  
  
      struct sockaddr_in{  
   short sin_family;  
   unsigned short sin_port;  
   struct in_addr sin_addr;  
   char sin_zero[8];  
};  
```  
  
#### Parameter  
 *sin\_family*  
 Adressenfamilie \(muss **AF\_INET** sein\).  
  
 *sin\_port*  
 IP\-Port.  
  
 *sin\_addr*  
 IP\-Adresse.  
  
 *sin\_zero*  
 Auffüllung, um die Struktur ebenso groß wie `SOCKADDR` zu machen.  
  
## Hinweise  
 Dies ist die Form der `SOCKADDR`\-Struktur speziell für die Internetadressenfamilie; sie kann in `SOCKADDR` umgewandelt werden.  
  
 Die IP\-Adressenkomponente dieser Struktur ist vom Typ **IN\_ADDR**.  Die **IN\_ADDR**\-Struktur wird in der Windows Sockets\-Headerdatei WINSOCK.H wie folgt definiert:  
  
 `struct   in_addr {`  
  
 `union   {`  
  
 `struct{`  
  
 `unsigned  char   s_b1,`  
  
 `s_b2,`  
  
 `s_b3,`  
  
 `s_b4;`  
  
 `}  S_un_b;`  
  
 `struct  {`  
  
 `unsigned  short  s_w1,`  
  
 `s_w2;`  
  
 `}  S_un_w;`  
  
 `unsigned long  S_addr;`  
  
 `} S_un;`  
  
 `};`  
  
## Anforderungen  
 **Header:** winsock2.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [SOCKADDR\-Struktur](../../mfc/reference/sockaddr-structure.md)