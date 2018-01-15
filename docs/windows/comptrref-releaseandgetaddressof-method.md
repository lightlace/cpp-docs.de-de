---
title: 'Comptrref:: Releaseandgetaddressof-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::Details::ComPtrRef::ReleaseAndGetAddressOf
dev_langs: C++
helpviewer_keywords: ReleaseAndGetAddressOf method
ms.assetid: 004aac42-e135-41ce-8d1d-4c5969d55004
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b7870e6149f1820040f147c0ec7142050fb0098b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="comptrrefreleaseandgetaddressof-method"></a>ComPtrRef::ReleaseAndGetAddressOf-Methode
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
InterfaceType** ReleaseAndGetAddressOf();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Zeiger auf die Schnittstelle, die durch das gelöschte ComPtrRef-Objekt dargestellt wurde.  
  
## <a name="remarks"></a>Hinweise  
 Löscht die aktuelle ComPtrRef-Objekt und gibt einen Zeiger-auf-a-Zeiger auf die Schnittstelle, die vom ComPtrRef-Objekt dargestellt wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [ComPtrRef-Klasse](../windows/comptrref-class.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)