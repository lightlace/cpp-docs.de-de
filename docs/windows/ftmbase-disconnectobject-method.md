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
ms.openlocfilehash: b467162d2f5cc5b04bc43a6d31019eb08e17e750
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595405"
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