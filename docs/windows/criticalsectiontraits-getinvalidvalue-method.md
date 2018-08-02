---
title: 'Criticalsectiontraits:: Getinvalidvalue-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue
dev_langs:
- C++
helpviewer_keywords:
- GetInvalidValue method
ms.assetid: 665f30a6-ca9c-4968-8c03-8f84e6b2329b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cf0d52769052a36c0b494d19204dd6c07f0b2404
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463384"
---
# <a name="criticalsectiontraitsgetinvalidvalue-method"></a>CriticalSectionTraits::GetInvalidValue-Methode
Spezialisiert hat eine **CriticalSection** Vorlage so, dass die Vorlage immer ungültig ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
inline static Type GetInvalidValue();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt immer einen Zeiger auf einen ungültigen kritischen Abschnitt zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die *Typ* Modifizierer ist definiert als `typedef CRITICAL_SECTION* Type;`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Siehe auch  
 [CriticalSectionTraits-Struktur](../windows/criticalsectiontraits-structure.md)