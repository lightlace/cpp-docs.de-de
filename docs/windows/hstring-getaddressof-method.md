---
title: 'Hstring:: Getaddressof-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::GetAddressOf
dev_langs:
- C++
ms.assetid: 6050decf-5f99-49f0-9497-1c8192c485ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7d4804373045d12c2e251e2de61b7aefd52ec916
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="hstringgetaddressof-method"></a>HString::GetAddressOf-Methode
Ruft einen Zeiger auf das zugrunde liegende HSTRING-Handle ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HSTRING* GetAddressOf() throw()  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das zugrunde liegende HSTRING-Handle.  
  
## <a name="remarks"></a>Hinweise  
 Nach diesem Vorgang wird der Zeichenfolgenwert des zugrunde liegenden HSTRING-Handles zerstört.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HString-Klasse](../windows/hstring-class.md)