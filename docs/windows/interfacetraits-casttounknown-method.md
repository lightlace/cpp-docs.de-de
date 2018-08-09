---
title: 'Interfacetraits:: Casttounknown-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToUnknown
dev_langs:
- C++
helpviewer_keywords:
- CastToUnknown method
ms.assetid: aca47fa0-3c60-47f2-a73c-258f7160adff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bdb87fe43b5cc6a5d2c141ac534e3b5e781f91e8
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40019916"
---
# <a name="interfacetraitscasttounknown-method"></a>InterfaceTraits::CastToUnknown-Methode
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
template<typename T>  
static __forceinline IUnknown* CastToUnknown(  
   _In_ T* ptr  
);  
```  
  
### <a name="parameters"></a>Parameter  
 *T*  
 Der Typ des Parameters *Ptr*.  
  
 *ptr*  
 Zeiger auf den Typ *T*.  
  
## <a name="return-value"></a>Rückgabewert  
 Zeiger auf IUnknown aus dem `Base` abgeleitet ist.  
  
## <a name="remarks"></a>Hinweise  
 Wandelt den angegebenen Zeiger auf einen Zeiger auf `IUnknown`.  
  
 Weitere Informationen zu `Base`, finden Sie im Abschnitt Öffentliche Typedefs [InterfaceTraits-Struktur](../windows/interfacetraits-structure.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [InterfaceTraits-Struktur](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)