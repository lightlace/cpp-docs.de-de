---
title: 'Handletraits:: Close-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close
dev_langs: C++
helpviewer_keywords: Close method
ms.assetid: 3c631a7c-ccce-472a-b1da-aab8fa815c13
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b1acb5125f8d38704b805885ad318c2bd301bcb7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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