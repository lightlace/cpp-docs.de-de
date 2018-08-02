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
ms.openlocfilehash: 0ff18dee2b8d951ab9233e92478eb967e4a02eb9
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464297"
---
# <a name="comptroperator-gt-operator"></a>Comptr:: -&gt; Operator
Ruft einen Zeiger auf den Typ ab, der durch den aktuellen Vorlagenparameter angegeben ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
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