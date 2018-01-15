---
title: 'Implements:: cancastto-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Implements::CanCastTo
dev_langs: C++
helpviewer_keywords: CanCastTo method
ms.assetid: a8e85c7d-4dcd-446d-bebc-a97da46ce44a
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f1607b5fc290c398350b9e5c9d81eb50088b61c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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