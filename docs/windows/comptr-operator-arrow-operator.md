---
title: 'Comptr:: -&gt; Operator | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator->
dev_langs:
- C++
helpviewer_keywords:
- operator-> operator
ms.assetid: 7b7faefd-d1e4-4f31-a77d-17a42e0d6b6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1530f7998f2597aeb2fe46dba09f4844b471cd93
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644829"
---
# <a name="comptroperator-gt-operator"></a>Comptr:: -&gt; Operator
Ruft einen Zeiger auf den Typ ab, der durch den aktuellen Vorlagenparameter angegeben ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Zeiger auf den Typ, von der aktuellen vorlagentypname angegeben.  
  
## <a name="remarks"></a>Hinweise  
 Diese Hilfsfunktion entfernt unnötigen Mehraufwand verursacht werden, die STDMETHOD-Makro. Diese Funktion macht `IUnknown` Typen **private** anstelle von **virtuellen**.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ComPtr-Klasse](../windows/comptr-class.md)