---
title: 'Dontusenewusemake:: new-Operator | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new
dev_langs:
- C++
helpviewer_keywords:
- operator new operator
ms.assetid: 6af07a0d-2271-430c-9d9b-5a4223fed049
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9785ea27c79ff0a118ff3697a22804c520b265ee
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873679"
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