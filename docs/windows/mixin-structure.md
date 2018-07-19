---
title: MixIn-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::MixIn
dev_langs:
- C++
helpviewer_keywords:
- MixIn structure
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b20dac5f189a51a1610da45e43e03e51ff1c3610
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876162"
---
# <a name="mixin-structure"></a>MixIn-Struktur
Stellt sicher, dass eine Runtime-Klasse aus Windows-Runtime-Schnittstellen (sofern vorhanden) und dann aus klassischen COM-Schnittstellen abgeleitet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<  
   typename Derived,  
   typename MixInType,  
   bool hasImplements = __is_base_of(Details::ImplementsBase,  
   MixInType)  
>  
struct MixIn;  
```  
  
#### <a name="parameters"></a>Parameter  
 `Derived`  
 Ein abgeleiteter Typ aus der [implementiert](../windows/implements-structure.md) Struktur.  
  
 `MixInType`  
 Ein Basistyp.  
  
 `hasImplements`  
 `true` Wenn `MixInType` ist abgeleitet von der aktuellen Implementierung den Basistyp; `false` andernfalls.  
  
## <a name="remarks"></a>Hinweise  
 Wenn eine Klasse von Windows-Runtime und COM-Klassenschnittstellen abgeleitet ist, die Deklaration Klassenliste muss zuerst aufgeführt werden keine Windows-Runtime-Schnittstellen, und klicken Sie dann alle klassischen COM-Schnittstellen. "Mixin" wird sichergestellt, dass die Schnittstellen in der richtigen Reihenfolge angegeben werden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `MixIn`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)