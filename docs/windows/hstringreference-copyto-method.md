---
title: 'Hstringreference:: CopyTo-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 179d9b14-1ced-4b16-b297-19ca1e92a462
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fcd27ab7132739987859024270ac6c82be06e590
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39607792"
---
# <a name="hstringreferencecopyto-method"></a>HStringReference::CopyTo-Methode
Kopiert das aktuelle **HStringReference** Objekt zu einem HSTRING-Objekt.  
  
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
 [HStringReference-Klasse](../windows/hstringreference-class.md)