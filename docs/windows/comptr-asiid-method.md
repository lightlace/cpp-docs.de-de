---
title: 'Comptr:: Asiid-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 07/11/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::AsIID
dev_langs:
- C++
helpviewer_keywords:
- AsIID method
ms.assetid: d5a3cdb2-796d-4410-966a-847c0e8fb226
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 32f75c838ea178b1313ab0bf9f005ff2a4c5d75b
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652561"
---
# <a name="comptrasiid-method"></a>ComPtr::AsIID-Methode
Gibt eine **ComPtr** Objekt, das die Schnittstelle, die die angegebene Schnittstellen-ID identifizierte darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
WRL_NOTHROW HRESULT AsIID(  
   REFIID riid,  
   _Out_ ComPtr<IUnknown>* p  
) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *riid*  
 Eine Schnittstellen-ID.  
  
 *p*  
 Wenn das Objekt eine Schnittstelle verfügt, deren ID gleich *Riid*, ein doppelt indirekter Zeiger auf die angegebene Schnittstelle die *Riid* Parameter ist, andernfalls ein Zeiger auf `IUnknown`.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ComPtr-Klasse](../windows/comptr-class.md)