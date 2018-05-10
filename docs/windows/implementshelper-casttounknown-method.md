---
title: 'Implementshelper:: Casttounknown-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper::CastToUnknown
dev_langs:
- C++
helpviewer_keywords:
- CastToUnknown method
ms.assetid: 5bcfcbaf-c75f-4d43-87b3-0d6838c838d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e5a5c71fd0a6ca8fa3b04ad39f46ba5583fbd670
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="implementshelpercasttounknown-method"></a>ImplementsHelper::CastToUnknown-Methode
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
IUnknown* CastToUnknown();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die zugrunde liegende IUnknown-Schnittstelle.  
  
## <a name="remarks"></a>Hinweise  
 Ruft einen Zeiger auf die zugrunde liegenden IUnknown-Schnittstelle für die aktuelle Implements-Struktur.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [ImplementsHelper-Struktur](../windows/implementshelper-structure.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)