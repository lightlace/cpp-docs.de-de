---
title: 'Dontusenewusemake:: new-Operator | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new
dev_langs: C++
helpviewer_keywords: operator new operator
ms.assetid: 6af07a0d-2271-430c-9d9b-5a4223fed049
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ea5cfa85dcf2873dcb8fe287e251511e3e48dbb8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="dontusenewusemakeoperator-new-operator"></a>DontUseNewUseMake::operator new-Operator
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
void* operator new(  
   size_t,  
   _In_ void* placement  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `__unnamed0`  
 Einen unbenannten Parameter, der die Anzahl der Bytes des zu belegenden Speichers angibt.  
  
 `placement`  
 Der Typ zugeordnet werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Bietet eine Möglichkeit, zusätzliche Argumente zu übergeben, wenn Sie beim Überladen `new`.  
  
## <a name="remarks"></a>Hinweise  
 Überlädt `new` und verhindert, dass er im RuntimeClass verwendet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [DontUseNewUseMake-Klasse](../windows/dontusenewusemake-class.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)