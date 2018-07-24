---
title: 'Comptrref:: Operator Void **-Operator | Microsoft-Dokumentation'
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
ms.openlocfilehash: 9fb3cd0a4c180073499ec1bdde1ea4703ffbf9e8
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207851"
---
# <a name="comptrrefoperator-void-operator"></a>Comptrref:: "void"\* \* Operator
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
operator void**() const;  
```  
  
## <a name="remarks"></a>Hinweise  
 Löscht das aktuelle ComPtrRef-Objekt, wandelt den Zeiger auf die Schnittstelle, die vom ComPtrRef-Objekt dargestellt wird, als eine Zeiger-auf-Zeiger-auf `void`, und klicken Sie dann die Cast-Zeiger zurückgibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [ComPtrRef-Klasse](../windows/comptrref-class.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)
