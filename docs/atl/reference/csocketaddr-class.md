---
title: "CSocketAddr Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CSocketAddr"
  - "ATL.CSocketAddr"
  - "ATL::CSocketAddr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSocketAddr class"
ms.assetid: 2fb2d8a7-899e-4a36-a342-cc9f4fcdd68c
caps.latest.revision: 19
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CSocketAddr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Konvertieren von Hostnamen zu den Hostadressen bereit und unterstützt Stile IPv4 und IPV6.  
  
## Syntax  
  
```  
  
class CSocketAddr  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSocketAddr::CSocketAddr](../Topic/CSocketAddr::CSocketAddr.md)|Der \-Konstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSocketAddr::FindAddr](../Topic/CSocketAddr::FindAddr.md)|Rufen Sie diese Methode auf, um den angegebenen Hostnamen zum host IP\-Adressen zu konvertieren.|  
|[CSocketAddr::FindINET4Addr](../Topic/CSocketAddr::FindINET4Addr.md)|Rufen Sie diese Methode auf, um den Hostnamen IPv4 zum host IP\-Adressen zu konvertieren.|  
|[CSocketAddr::FindINET6Addr](../Topic/CSocketAddr::FindINET6Addr.md)|Rufen Sie diese Methode auf, um den Hostnamen IPv6 zum host IP\-Adressen zu konvertieren.|  
|[CSocketAddr::GetAddrInfo](../Topic/CSocketAddr::GetAddrInfo.md)|Rufen Sie diese Methode auf, um einen Zeiger auf ein bestimmtes Element in der Liste **addrinfo** zurückzugeben.|  
|[CSocketAddr::GetAddrInfoList](../Topic/CSocketAddr::GetAddrInfoList.md)|Rufen Sie diese Methode auf, um einen Zeiger auf die **addrinfo** Liste zurückgegeben.|  
  
## Hinweise  
 Diese Klasse bietet einen agnostischen Ansatz IP\-Version für Endsystemadressen nach dem oben suchen mit Windows Socket\-API\-Funktions\- und \-Socketwrappern in Bibliotheken.  
  
 Die Member dieser Klasse, die verwendet werden, um Endsystemadressen gesucht wird, verwenden die Win32\-API [getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520).  
  
 Diese Klasse unterstützt beide Endsystemadressen IPv4 andIPv6.  
  
## Anforderungen  
 **Header:** atlsocket.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)