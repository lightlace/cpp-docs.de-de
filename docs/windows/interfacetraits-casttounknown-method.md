---
title: 'Interfacetraits:: Casttounknown-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::InterfaceTraits::CastToUnknown
dev_langs: C++
helpviewer_keywords: CastToUnknown method
ms.assetid: aca47fa0-3c60-47f2-a73c-258f7160adff
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e14c5e70c4854e1f3263a26a0075373248ae9d90
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="interfacetraitscasttounknown-method"></a>InterfaceTraits::CastToUnknown-Methode
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<  
   typename T  
>  
static __forceinline IUnknown* CastToUnknown(  
   _In_ T* ptr  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ des Parameters `ptr`.  
  
 `ptr`  
 Zeiger auf den Typ `T`.  
  
## <a name="return-value"></a>Rückgabewert  
 Zeiger auf das IUnknown aus dem `Base` abgeleitet ist.  
  
## <a name="remarks"></a>Hinweise  
 Wandelt den angegebenen Zeiger auf ein IUnknown-Zeiger.  
  
 Weitere Informationen zu `Base`, finden Sie im Abschnitt Öffentliche Typedefs [InterfaceTraits-Struktur](../windows/interfacetraits-structure.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [InterfaceTraits-Struktur](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)