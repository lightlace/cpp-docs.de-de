---
title: 'Weakref:: Weakref-Konstruktor | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::WeakRef
dev_langs:
- C++
helpviewer_keywords:
- WeakRef, constructor
ms.assetid: 589f87e0-8dcc-4e82-aab2-f2f66f1ec47c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6e7b7d35fd8cae44c3f374a81cae572e4c9ee4f8
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011158"
---
# <a name="weakrefweakref-constructor"></a>WeakRef::WeakRef-Konstruktor
Initialisiert eine neue Instanz der dem **WeakRef** Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
  
### <a name="parameters"></a>Parameter  
 *ptr*  
 Ein Zeiger, Verweis oder Rvalue-Verweis auf ein vorhandenes Objekt, das das aktuelle initialisiert **WeakRef** Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Der erste Konstruktor initialisiert ein leeres **WeakRef** Objekt. Der zweite Konstruktor initialisiert ein **WeakRef** Objekt von einem Zeiger auf die `IWeakReference` Schnittstelle. Der dritte Konstruktor initialisiert ein **WeakRef** Objekt aus einem Verweis auf eine `ComPtr<IWeakReference>` Objekt. Der vierte und fünfte Konstruktor initialisiert ein **WeakRef** Objekt von einem anderen **WeakRef** Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [WeakRef-Klasse](../windows/weakref-class.md)