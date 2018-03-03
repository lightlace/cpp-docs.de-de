---
title: SOCKADDR-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SOCKADDR
dev_langs:
- C++
helpviewer_keywords:
- SOCKADDR structure [MFC]
ms.assetid: df1ed66a-f4b8-43f8-8db8-8c2533d25f68
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 55b310ec83aae35c7386d61849663752811651d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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

