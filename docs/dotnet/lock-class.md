---
title: Lock-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- msclr::lock
- msclr.lock
- lock
dev_langs: C++
helpviewer_keywords: lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2c9e21612c227081e3558a8f7f3161f922711c20
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="lock-class"></a>lock-Klasse
Diese Klasse automatisiert die Sperre für den Zugriff auf ein Objekt von mehreren Threads synchronisieren.  Wenn erstellt er die Sperre erhält und, wenn es sich um Releases zerstört die Sperre.  
  
## <a name="syntax"></a>Syntax  
  
```  
ref class lock;  
```  
  
## <a name="remarks"></a>Hinweise  
 `lock`ist nur für CLR-Objekte verfügbar und kann nur in CLR-Code verwendet werden.  
  
 Intern wird die Sperre-Klasse verwendet <xref:System.Threading.Monitor> zum Synchronisieren des Zugriffs. Finden Sie dieses Thema enthält weitere ausführliche Informationen zur Synchronisierung aus.  
  
## <a name="requirements"></a>Anforderungen  
 **Headerdatei** \<msclr\lock.h >  
  
 **Namespace** Msclr  
  
## <a name="see-also"></a>Siehe auch  
 [Sperre](../dotnet/lock.md)   
 [lock-Members](../dotnet/lock-members.md)