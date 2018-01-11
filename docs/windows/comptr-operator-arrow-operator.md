---
title: 'Comptr:: -&gt; Operator | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::operator->
dev_langs: C++
helpviewer_keywords: operator-> operator
ms.assetid: 7b7faefd-d1e4-4f31-a77d-17a42e0d6b6a
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3c70c37523132d06bfb04c86cf6f737109da43e2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="comptroperator-gt-operator"></a>Comptr:: -&gt; Operator
Ruft einen Zeiger auf den Typ ab, der durch den aktuellen Vorlagenparameter angegeben ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Zeiger auf den Typ, der von der aktuellen vorlagentypname angegeben.  
  
## <a name="remarks"></a>Hinweise  
 Diese Hilfsfunktion entfernt unnötigen Aufwand verursacht werden, das STDMETHOD-Makro. Diese Funktion macht IUnknown-Typen anstelle von virtuellen privaten.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ComPtr-Klasse](../windows/comptr-class.md)