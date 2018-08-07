---
title: 'Handletraits:: Close-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 3c631a7c-ccce-472a-b1da-aab8fa815c13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 581c7b8447b800d9a3401cd76f3adc5ada25994d
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569829"
---
# <a name="handletraitsclose-method"></a>HANDLETraits::Close-Methode
Schließt das angegebene Handle.  
  
## <a name="syntax"></a>Syntax  
  
```  
inline static bool Close(  
   _In_ Type h  
);  
```  
  
### <a name="parameters"></a>Parameter  
 *h*  
 Das Handle zu schließen.  
  
## <a name="return-value"></a>Rückgabewert  
 **"true"** Wenn behandeln *h* geschlossen wird, erfolgreich ist; andernfalls **"false"**.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Siehe auch  
 [HANDLETraits-Struktur](../windows/handletraits-structure.md)