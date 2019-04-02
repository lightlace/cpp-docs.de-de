---
title: CreateActivationFactory-Funktion
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateActivationFactory
helpviewer_keywords:
- CreateActivationFactory function
ms.assetid: a1a53e04-6757-4faf-a4c8-ecf06e43b959
ms.openlocfilehash: 07bc0dceb8066faf9c1beab64d48245d8735aa64
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785602"
---
# <a name="createactivationfactory-function"></a>CreateActivationFactory-Funktion

Erstellt eine Instanzen der angegebenen Klasse erstellende Factory, die durch die Windows-Runtime aktiviert werden kann.

## <a name="syntax"></a>Syntax

```cpp
template<typename Factory>
   inline HRESULT STDMETHODCALLTYPE CreateActivationFactory(
      _In_ unsigned int *flags,        _In_ const CreatorMap* entry,
      REFIID riid,
   _Outptr_ IUnknown **ppFactory) throw();
```

### <a name="parameters"></a>Parameter

*flags*<br/>
Eine Kombination aus einem oder mehreren [RuntimeClassType](runtimeclasstype-enumeration.md) -Enumerationswerte fest.

*entry*<br/>
Zeiger auf eine [CreatorMap](creatormap-structure.md) mit Initialisierungs- und Registrierung Informationen zum Parameter *Riid*.

*riid*<br/>
Verweis auf eine Schnittstellen-ID.

*ppFactory*<br/>
Wenn dieser Vorgang erfolgreich, einen Zeiger auf eine aktivierungsfactory ausgeführt wird.

## <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="remarks"></a>Hinweise

Ein Assert-Fehler wird ausgegeben, wenn Vorlagenparameter *Factory* nicht abgeleitet werden, aus der Schnittstelle `IActivationFactory`.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Wrappers::Details-Namespace](microsoft-wrl-wrappers-details-namespace.md)