---
title: 'Hstring:: CopyTo-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: a1fd2ef0-e175-4c18-927b-550e02a89e43
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8dd0cab708832a9872c55c53ad058fe0cd78e6bb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="hstringcopyto-method"></a>HString::CopyTo-Methode
Kopiert das aktuelle HString-Objekt zu einem HSTRING-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
HRESULT CopyTo(  
   _Out_ HSTRING *str  
   ) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `str`  
 Das HSTRING, das die Kopie erhält.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ruft die [WindowsDuplicateString](http://msdn.microsoft.com/library/br224634.aspx) Funktion.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HString-Klasse](../windows/hstring-class.md)