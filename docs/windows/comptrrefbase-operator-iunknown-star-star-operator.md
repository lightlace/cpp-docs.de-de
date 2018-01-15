---
title: 'Comptrrefbase:: Operator IUnknown **-Operator | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown**
dev_langs: C++
helpviewer_keywords: operator IUnknown** operator
ms.assetid: c2950abf-a7aa-480a-ba41-615703e7f931
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 04eaa2992c74b4cb46954ac73aa7b5a8ae735f82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="comptrrefbaseoperator-iunknown-operator"></a>ComPtrRefBase::operator IUnknown**-Operator
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
operator IUnknown**() const;  
```  
  
## <a name="remarks"></a>Hinweise  
 Wandelt das aktuelle [Ptr_](../windows/comptrrefbase-ptr-data-member.md) -Datenmember auf einen Zeiger an eine-Zeiger-an der IUnknown-Schnittstelle.  
  
 Ein Fehler wird ausgegeben, wenn die aktuelle ComPtrRefBase von IUnknown abgeleitet werden, nicht.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [ComPtrRefBase-Klasse](../windows/comptrrefbase-class.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)