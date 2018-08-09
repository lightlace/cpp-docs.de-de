---
title: 'Ftmbase:: DisconnectObject-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::DisconnectObject
dev_langs:
- C++
helpviewer_keywords:
- DisconnectObject method
ms.assetid: 33253eec-3a65-4e72-8525-0249245a4790
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0bb6b6be87736d55eabc6b487101ec68fc16e378
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646139"
---
# <a name="ftmbasedisconnectobject-method"></a>FtmBase::DisconnectObject-Methode
Zwangsweise veröffentlicht alle externe Verbindungen zu einem Objekt. Das Objekt der Server Ruft die Implementierung dieser Methode vor dem Herunterfahren des Objekts.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
STDMETHODIMP DisconnectObject(  
   __in DWORD dwReserved  
) override;  
```  
  
### <a name="parameters"></a>Parameter  
 *dwReserved*  
 Für die zukünftige Verwendung reserviert. Muss 0 (null) sein.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [FtmBase-Klasse](../windows/ftmbase-class.md)