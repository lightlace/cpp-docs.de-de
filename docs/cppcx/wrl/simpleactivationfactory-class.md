---
title: SimpleActivationFactory-Klasse
ms.date: 09/07/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory
- module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance
- module/Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName
- module/Microsoft::WRL::SimpleActivationFactory::GetTrustLevel
helpviewer_keywords:
- Microsoft::WRL::SimpleActivationFactory class
- Microsoft::WRL::SimpleActivationFactory::ActivateInstance method
- Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName method
- Microsoft::WRL::SimpleActivationFactory::GetTrustLevel method
ms.assetid: aff768e0-0038-4fd7-95d2-ad7d308da41c
ms.openlocfilehash: 1831a816d0967c2ca53f941128639ea368c1b727
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403085"
---
# <a name="simpleactivationfactory-class"></a>SimpleActivationFactory-Klasse

Stellt einen grundlegenden Mechanismus für das Erstellen einer Windows-Runtime oder einer klassischen COM-Basisklasse bereit.

## <a name="syntax"></a>Syntax

```cpp
template<typename Base>
class SimpleActivationFactory : public ActivationFactory<>;
```

### <a name="parameters"></a>Parameter

*Basis*<br/>
Eine Basisklasse.

## <a name="remarks"></a>Hinweise

Die Basisklasse muss einen Standardkonstruktor bereitstellen.

Im folgenden Codebeispiel wird veranschaulicht, wie mit SimpleActivationFactory mit der [ActivatableClassWithFactoryEx](activatableclass-macros.md) Makro.

`ActivatableClassWithFactoryEx(MyClass, SimpleActivationFactory, MyServerName);`

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[SimpleActivationFactory::ActivateInstance-Methode](#activateinstance)|Erstellt eine Instanz der angegebenen Schnittstelle.|
|[SimpleActivationFactory::GetRuntimeClassName-Methode](#getruntimeclassname)|Ruft den Common Language Runtime-Klassennamen einer Instanz der Klasse gemäß den *Base* Klassenvorlagenparameter.|
|[SimpleActivationFactory::GetTrustLevel-Methode](#gettrustlevel)|Ruft die Vertrauensebene der eine Instanz der Klasse, die gemäß der *Base* Klassenvorlagenparameter.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`I0`

`ChainInterfaces`

`I0`

`RuntimeClassBase`

`ImplementsHelper`

`DontUseNewUseMake`

`RuntimeClassFlags`

`RuntimeClassBaseT`

`RuntimeClass`

`ActivationFactory`

`SimpleActivationFactory`

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="activateinstance"></a>Simpleactivationfactory:: Activateinstance-Methode

Erstellt eine Instanz der angegebenen Schnittstelle.

```cpp
STDMETHOD( ActivateInstance )(
    _Deref_out_ IInspectable **ppvObject
);
```

#### <a name="parameters"></a>Parameter

*ppvObject*<br/>
Wenn dieser Vorgang abgeschlossen ist, Zeiger auf eine Instanz des Objekts gemäß der `Base` Klassenvorlagenparameter.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

### <a name="remarks"></a>Hinweise

Wenn `__WRL_STRICT__` wird definiert, ein Assert-Fehler wird ausgegeben, wenn die Klassenvorlagenparameter angegebene Basisklasse abgeleitet ist nicht [RuntimeClass](runtimeclass-class.md), oder ist nicht konfiguriert, mit dem WinRt oder WinRtClassicComMix [ RuntimeClassType](runtimeclasstype-enumeration.md) Enumerationswert.

## <a name="getruntimeclassname"></a>Simpleactivationfactory:: Getruntimeclassname-Methode

Ruft den Common Language Runtime-Klassennamen einer Instanz der Klasse gemäß den `Base` Klassenvorlagenparameter.

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

#### <a name="parameters"></a>Parameter

*runtimeName*<br/>
Wenn dieser Vorgang abgeschlossen ist, den Namen der Common Language Runtime-Klasse.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

### <a name="remarks"></a>Hinweise

Wenn `__WRL_STRICT__` wird definiert, ein Assert-Fehler wird ausgegeben, wenn die Klasse, wird angegeben die `Base` Klassenvorlagenparameter wird nicht von abgeleiteten [RuntimeClass](runtimeclass-class.md), oder ist nicht mit dem WinRt oder WinRtClassicComMix konfiguriert[RuntimeClassType](runtimeclasstype-enumeration.md) Enumerationswert.

## <a name="gettrustlevel"></a>Simpleactivationfactory:: Gettrustlevel-Methode

Ruft die Vertrauensebene der eine Instanz der Klasse, die gemäß der `Base` Klassenvorlagenparameter.

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

#### <a name="parameters"></a>Parameter

*trustLvl*<br/>
Wenn dieser Vorgang abgeschlossen ist, die Vertrauensebene des aktuellen Klassenobjekts.

### <a name="return-value"></a>Rückgabewert

Stets S_OK.
