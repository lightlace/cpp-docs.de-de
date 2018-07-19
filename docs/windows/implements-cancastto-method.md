---
title: 'Implements:: cancastto-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements::CanCastTo
dev_langs:
- C++
helpviewer_keywords:
- CanCastTo method
ms.assetid: a8e85c7d-4dcd-446d-bebc-a97da46ce44a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4fd6e6736c74e1ce895031e17c1d5268eb4ce646
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877072"
---
# <a name="implementscancastto-method"></a>Implements::CanCastTo-Methode
Ruft einen Zeiger auf die angegebene Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```  
__forceinline HRESULT CanCastTo(  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `riid`  
 Ein Verweis auf eine Schnittstellen-ID.  
  
 `ppv`  
 Wenn erfolgreich, ein Zeiger auf die Schnittstelle von angegeben `riid`.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler, z. B. E_NOINTERFACE angibt.  
  
## <a name="remarks"></a>Hinweise  
 Dies ist eine interne Hilfsmethode-Funktion, die einen QueryInterface-Vorgang ausführt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Implements-Struktur](../windows/implements-structure.md)