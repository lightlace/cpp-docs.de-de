---
title: 'Comptrrefbase:: Operator IUnknown **-Operator | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown**
dev_langs:
- C++
helpviewer_keywords:
- operator IUnknown** operator
ms.assetid: c2950abf-a7aa-480a-ba41-615703e7f931
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 816c71d2c14b373e63de2b2c8725eb87b40d91e7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
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