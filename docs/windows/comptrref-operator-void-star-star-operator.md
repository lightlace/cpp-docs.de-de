---
title: 'Comptrref:: Operator Void **-Operator | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::operator void**
dev_langs:
- C++
helpviewer_keywords:
- operator void** operator
ms.assetid: f020045c-9de4-4392-8783-73f0fc0761c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3993cb0a5ce55996ae2ff793e83453040455aa7f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33887081"
---
# <a name="comptrrefoperator-void-operator"></a>ComPtrRef::operator void**-Operator
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
operator void**() const;  
```  
  
## <a name="remarks"></a>Hinweise  
 Löscht die aktuelle ComPtrRef-Objekt, wandelt den Zeiger auf die Schnittstelle, die vom ComPtrRef-Objekt dargestellt wurde, als ein Zeiger-auf-Zeiger-auf `void`, und klicken Sie dann die Cast-Zeiger zurückgibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [ComPtrRef-Klasse](../windows/comptrref-class.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)