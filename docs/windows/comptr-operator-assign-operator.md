---
title: 'Comptr:: Operator = | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 1a0c2752-f7d8-4819-9443-07b88b69ef02
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6b221ff75e250830feefbbd2d3db0d8697095c96
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="comptroperator-operator"></a>ComPtr::operator=-Operator
Weist dem aktuellen ComPtr-Objekt einen Wert zu.  
  
## <a name="syntax"></a>Syntax  
  
```  
WRL_NOTHROW ComPtr& operator=(  
   decltype(__nullptr)  
);  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ T *other  
);  
template <typename U>  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr &other  
);  
template<class U>  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr<U>& other  
);  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr &&other  
);  
template<class U>  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr<U>&& other  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `U`  
 Eine Klasse.  
  
 `other`  
 Ein Zeiger, Verweis oder Rvalue-Verweis auf einen Typ oder eine andere comptr-Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das aktuelle comptr-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Die erste Version dieses Operators weist einen leeren Wert zu dem aktuellen comptr-Objekt.  
  
 In der zweiten Version wird das Zuweisen von Schnittstellenzeiger nicht identisch mit den aktuellen ComPtr-Schnittstellenzeiger ist die zweite Schnittstellenzeiger auf dem aktuellen comptr-Objekt zugewiesen.  
  
 In der dritten Version ist das Zuweisen von Schnittstellenzeiger auf das aktuelle comptr-Objekt zugewiesen.  
  
 In der vierten Version wird der Schnittstellenzeiger auf das Zuweisen von Werts nicht mit den aktuellen ComPtr-Schnittstellenzeiger ist die zweite Schnittstellenzeiger auf das aktuelle comptr-Objekt zugewiesen.  
  
 Die fünfte Version ist eine Kopie-Operator. Ein Verweis auf ein comptr-Objekt wird auf dem aktuellen comptr-Objekt zugewiesen.  
  
 Der sechste Version ist ein Kopie-Operator, der verwendet die move-Semantik; Ein Rvalue-Verweis auf ein comptr-Objekt, wenn jeder Typ statisch ist, umgewandelt, und klicken Sie dann auf dem aktuellen comptr-Objekt zugewiesen werden soll.  
  
 Die siebte Version ist ein Kopie-Operator, der verwendet die move-Semantik; Ein Rvalue-Verweis auf ein comptr-Objekt des Typs `U` ist statisch dann umgewandelt und dem aktuellen comptr-Objekt zugewiesen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ComPtr-Klasse](../windows/comptr-class.md)