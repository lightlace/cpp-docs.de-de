---
title: ActivationFactoryCallback-Funktion
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::ActivationFactoryCallback
helpviewer_keywords:
- ActivationFactoryCallback function
ms.assetid: dd40c79b-1273-4f2a-8c24-ae9926fb4fd9
ms.openlocfilehash: 93db10e19cce0658bf731c14e7ac76b575841bf3
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785023"
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

[Microsoft::WRL::Details-Namespace](microsoft-wrl-details-namespace.md)