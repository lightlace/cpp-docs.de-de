---
title: 'WeakReference:: Setunknown-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::SetUnknown
dev_langs:
- C++
helpviewer_keywords:
- SetUnknown method
ms.assetid: 5dddb9e3-a7c1-4195-8166-97c5ab6e972f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 28b25645b21d3101e2f2b2004f02f29482320808
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891014"
---
# <a name="weakreferencesetunknown-method"></a>WeakReference::SetUnknown-Methode
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
void SetUnknown(  
   _In_ IUnknown* unk  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `unk`  
 Ein Zeiger auf die `IUnknown` Schnittstelle eines Objekts.  
  
## <a name="remarks"></a>Hinweise  
 Legt den starken Verweis des aktuellen `WeakReference` Objekt, das den angegebenen Schnittstellenzeiger auf.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch
[WeakReference-Klasse](../windows/weakreference-class1.md)  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)