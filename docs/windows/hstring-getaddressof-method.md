---
title: 'Hstring:: Getaddressof-Methode | Microsoft-Dokumentation'
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
ms.openlocfilehash: 4ea49833107bf58443bf4a8238229d1d63a86742
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010346"
---
# <a name="hstringgetaddressof-method"></a>HString::GetAddressOf-Methode
Ruft einen Zeiger auf das zugrunde liegende HSTRING-Handle ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HSTRING* GetAddressOf() throw()  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das zugrunde liegende HSTRING-Handle.  
  
## <a name="remarks"></a>Hinweise  
 Nach diesem Vorgang wird der Zeichenfolgenwert, der das zugrunde liegende HSTRING-Handle zerstört.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HString-Klasse](../windows/hstring-class.md)