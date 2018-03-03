---
title: 'Weakref:: Weakref-Konstruktor | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::WeakRef
dev_langs:
- C++
helpviewer_keywords:
- WeakRef, constructor
ms.assetid: 589f87e0-8dcc-4e82-aab2-f2f66f1ec47c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 125fe25179ddbe975530a0c368a4dfc7e4caaf1a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="weakrefweakref-constructor"></a>WeakRef::WeakRef-Konstruktor
Initialisiert eine neue Instanz der WeakRef-Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```  
WeakRef();  
WeakRef(  
   decltype(__nullptr)  
);  
  
WeakRef(  
   _In_opt_ IWeakReference* ptr  
);  
  
WeakRef(  
   const ComPtr<IWeakReference>& ptr  
);  
  
WeakRef(  
   const WeakRef& ptr  
);  
  
WeakRef(  
   _Inout_ WeakRef&& ptr  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ptr`  
 Ein Zeiger, ein Verweis oder ein Rvalue-Verweis auf ein vorhandenes Objekt, das das aktuelle WeakRef-Objekt initialisiert.  
  
## <a name="remarks"></a>Hinweise  
 Der erste Konstruktor initialisiert ein leeres WeakRef-Objekt. Der zweite Konstruktor initialisiert ein WeakRef-Objekt von einem Zeiger auf die Schnittstelle "iweakreference". Der dritte Konstruktor initialisiert ein WeakRef-Objekt aus einem Verweis auf ein ComPtr\< "iweakreference" > Objekt. Der vierte und fünfte Konstruktor initialisiert ein WeakRef-Objekt aus einem anderen WeakRef-Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [WeakRef-Klasse](../windows/weakref-class.md)