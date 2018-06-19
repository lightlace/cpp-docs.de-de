---
title: 'Handletraits:: Close-Methode | Microsoft Docs'
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
ms.openlocfilehash: 1f45f95fb1b060f3892def6dc2962bfffef70c77
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33875613"
---
# <a name="handletraitsclose-method"></a>HANDLETraits::Close-Methode
Schließt das angegebene Handle.  
  
## <a name="syntax"></a>Syntax  
  
```  
inline static bool Close(  
   _In_ Type h  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `h`  
 Das Handle zu schließen.  
  
## <a name="return-value"></a>Rückgabewert  
 **"true"** Wenn behandeln `h` geschlossen erfolgreich ist, andernfalls **"false"**.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Siehe auch  
 [HANDLETraits-Struktur](../windows/handletraits-structure.md)