---
title: ActivationFactoryCallback-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::ActivationFactoryCallback
dev_langs:
- C++
helpviewer_keywords:
- ActivationFactoryCallback function
ms.assetid: dd40c79b-1273-4f2a-8c24-ae9926fb4fd9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 62efb2b1aa2cd2caa0c5701696689ea3df19f962
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443610"
---
# <a name="activationfactorycallback-function"></a>ActivationFactoryCallback-Funktion

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
inline HRESULT STDAPICALLTYPE ActivationFactoryCallback(
   HSTRING activationId,
   IActivationFactory **ppFactory
);
```

### <a name="parameters"></a>Parameter

*activationId*<br/>
Handle für eine Zeichenfolge, die einen Common Language Runtime-Klassennamen angibt.

*ppFactory*<br/>
Wenn dieser Vorgang abgeschlossen ist, eine aktivierungsfactory, der Parameter entspricht *ActivationId*.

## <a name="return-value"></a>Rückgabewert

„S_OK“ im Erfolgsfall, andernfalls ein HRESULT, das den Fehler beschreibt. Wahrscheinlich Fehler-HRESULTs sind CLASS_E_CLASSNOTAVAILABLE und E_INVALIDARG zurückgegeben.

## <a name="remarks"></a>Hinweise

Ruft die aktivierungsfactory für die Aktivierung der angegebenen ID.

Die Windows-Runtime ruft diese Callback-Funktion, um ein Objekt, das durch den Namen der Common Language Runtime-Klasse angegebenen anzufordern.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)