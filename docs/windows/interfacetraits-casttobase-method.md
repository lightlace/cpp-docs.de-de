---
title: 'Interfacetraits:: Casttobase-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToBase
dev_langs:
- C++
helpviewer_keywords:
- CastToBase method
ms.assetid: 0591a017-0adf-4358-b946-eb0a307ce7f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4f284514472796f22d176325a0223848a827c85c
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606448"
---
# <a name="interfacetraitscasttobase-method"></a>InterfaceTraits::CastToBase-Methode
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename T>  
static __forceinline Base* CastToBase(  
   _In_ T* ptr  
);  
```  
  
### <a name="parameters"></a>Parameter  
 *T*  
 Der Typ des Parameters *Ptr*.  
  
 *ptr*  
 Zeiger auf einen Typ *T*.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf `Base`.  
  
## <a name="remarks"></a>Hinweise  
 Wandelt den angegebenen Zeiger auf einen Zeiger auf `Base`.  
  
 Weitere Informationen zu `Base`, finden Sie im Abschnitt Öffentliche Typedefs [InterfaceTraits-Struktur](../windows/interfacetraits-structure.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [InterfaceTraits-Struktur](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)