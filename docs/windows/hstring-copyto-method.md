---
title: 'Hstring:: CopyTo-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: a1fd2ef0-e175-4c18-927b-550e02a89e43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 65d8e259b74bcdffbf11c6c96172d918f9db1b50
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570872"
---
# <a name="hstringcopyto-method"></a>HString::CopyTo-Methode
Kopiert das aktuelle **HString** Objekt zu einem HSTRING-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CopyTo(  
   _Out_ HSTRING *str  
   ) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 *str*  
 Das HSTRING, das die Kopie erhält.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ruft die [WindowsDuplicateString](http://msdn.microsoft.com/library/br224634.aspx) Funktion.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HString-Klasse](../windows/hstring-class.md)