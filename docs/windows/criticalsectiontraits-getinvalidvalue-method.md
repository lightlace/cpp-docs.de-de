---
title: 'Criticalsectiontraits:: Getinvalidvalue-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue
dev_langs: C++
helpviewer_keywords: GetInvalidValue method
ms.assetid: 665f30a6-ca9c-4968-8c03-8f84e6b2329b
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 55bf0dedc286ed5dac8f48c7e8a2d43aa7741eff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="criticalsectiontraitsgetinvalidvalue-method"></a>CriticalSectionTraits::GetInvalidValue-Methode
CriticalSection Vorlage spezialisiert, damit, dass die Vorlage immer ungültig ist.  
  
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