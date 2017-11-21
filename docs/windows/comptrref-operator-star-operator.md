---
title: 'Comptrref:: * Operator | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::Details::ComPtrRef::operator*
dev_langs: C++
helpviewer_keywords: operator* operator
ms.assetid: 0287ca7a-4ce1-47f7-bab6-714fca3e04bb
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 543f0099a3c6b60d8e6ec289ff560b1ffc4169e2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="comptrrefoperator-operator"></a>ComPtrRef::operator*-Operator
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
InterfaceType* operator *();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Zeiger auf die Schnittstelle, die vom aktuellen ComPtrRef-Objekt dargestellt wird.  
  
## <a name="remarks"></a>Hinweise  
 Ruft ab, die Zeiger auf die Schnittstelle, die vom aktuellen ComPtrRef-Objekt dargestellt wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [ComPtrRef-Klasse](../windows/comptrref-class.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)