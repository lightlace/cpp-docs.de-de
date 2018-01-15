---
title: 'Interfacetraits:: Cancastto-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::InterfaceTraits::CanCastTo
dev_langs: C++
helpviewer_keywords: CanCastTo method
ms.assetid: 275847cb-69ea-42bf-910f-05ba6ef8b48d
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3d8dfe6c1873d9cf897494eb6157c2be3baeb435
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="interfacetraitscancastto-method"></a>InterfaceTraits::CanCastTo-Methode
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
template<typename T>  
static __forceinline bool CanCastTo(  
   _In_ T* ptr,  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `ptr`  
 Der Name eines Zeigers auf einen Typ.  
  
 `riid`  
 Der Schnittstellen-ID des `Base`.  
  
 `ppv`  
 Wenn dieser Vorgang erfolgreich ist, ist `ppv` verweist auf die angegebene Schnittstelle `Base`. Andernfalls `ppv` festgelegt ist, um `nullptr`.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`Wenn dieser Vorgang erfolgreich ist und `ptr` umgewandelt wird, in einen Zeiger auf `Base`ist, andernfalls `false` .  
  
## <a name="remarks"></a>Hinweise  
 Gibt an, ob der angegebene Zeiger umgewandelt werden kann, in einen Zeiger auf `Base`.  
  
 Weitere Informationen zu `Base`, finden Sie im Abschnitt Öffentliche Typedefs [InterfaceTraits-Struktur](../windows/interfacetraits-structure.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [InterfaceTraits-Struktur](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)