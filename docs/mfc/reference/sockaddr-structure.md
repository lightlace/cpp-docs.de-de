---
title: SOCKADDR-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SOCKADDR
dev_langs: C++
helpviewer_keywords: SOCKADDR structure [MFC]
ms.assetid: df1ed66a-f4b8-43f8-8db8-8c2533d25f68
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3ce8207ea1e8f82b635029861493262a5f6237f3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="sockaddr-structure"></a>SOCKADDR-Struktur
Die `SOCKADDR`-Struktur wird verwendet, um die Adresse eines Internetprotokolls (IP) für einen Computer zu speichern, der an einer Windows Socket-Kommunikation teilnimmt.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct sockaddr {  
    unsigned short sa_family;  
    char sa_data[14];  
};  
```  
  
#### <a name="parameters"></a>Parameter  
 *sa_family*  
 Socketadressenfamilie.  
  
 *sa_data*  
 Maximale Größe aller verschiedenen Socketadress-Strukturen.  
  
## <a name="remarks"></a>Hinweise  
 Das Microsoft TCP/IP-Kit des Socket-Entwicklers unterstützt nur die Internetadressendomänen. Um Werte für jeden Teil einer Adresse zu füllen, verwenden Sie die Datenstruktur von `SOCKADDR_IN`, die speziell für dieses Adressenformat vorgesehen ist. Die Datenstrukturen `SOCKADDR` und `SOCKADDR_IN` haben die gleiche Größe. Sie müssen einfach nur umschalten, um zwischen den beiden Strukturtypen zu wechseln.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winsock2.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [SOCKADDR_IN-Struktur](../../mfc/reference/sockaddr-in-structure.md)   
 [CAsyncSocket::Create](../../mfc/reference/casyncsocket-class.md#create)   
 [CSocket::Create](../../mfc/reference/csocket-class.md#create)

