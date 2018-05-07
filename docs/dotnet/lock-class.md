---
title: Lock-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::lock
- msclr.lock
- lock
dev_langs:
- C++
helpviewer_keywords:
- lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a860f79b740e0f34eef33b7a96e0236835f1f6b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="lock-class"></a>lock-Klasse
Diese Klasse automatisiert die Sperre für den Zugriff auf ein Objekt von mehreren Threads synchronisieren.  Wenn erstellt er die Sperre erhält und, wenn es sich um Releases zerstört die Sperre.  
  
## <a name="syntax"></a>Syntax  
  
```  
ref class lock;  
```  
  
## <a name="remarks"></a>Hinweise  
 `lock` ist nur für CLR-Objekte verfügbar und kann nur in CLR-Code verwendet werden.  
  
 Intern wird die Sperre-Klasse verwendet <xref:System.Threading.Monitor> zum Synchronisieren des Zugriffs. Finden Sie dieses Thema enthält weitere ausführliche Informationen zur Synchronisierung aus.  
  
## <a name="requirements"></a>Anforderungen  
 **Headerdatei** \<msclr\lock.h >  
  
 **Namespace** Msclr  
  
## <a name="see-also"></a>Siehe auch  
 [lock](../dotnet/lock.md)   
 [lock-Members](../dotnet/lock-members.md)