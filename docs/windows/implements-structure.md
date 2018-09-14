---
title: Struktur implementiert | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/11/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements
- implements/Microsoft::WRL::Implements::CanCastTo
- implements/Microsoft::WRL::Implements::CastToUnknown
- implements/Microsoft::WRL::Implements::FillArrayWithIid
- implements/Microsoft::WRL::Implements::IidCount
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Implements structure
- Microsoft::WRL::Implements::CanCastTo method
- Microsoft::WRL::Implements::CastToUnknown method
- Microsoft::WRL::Implements::FillArrayWithIid method
- Microsoft::WRL::Implements::IidCount method
ms.assetid: 29b13e90-34d4-4a0b-babd-5187c9eb0c36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 18616b1010dfe6a23861c512b1113c30fe5251ce
ms.sourcegitcommit: b4432d30f255f0cb58dce69cbc8cbcb9d44bc68b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45535352"
---
# <a name="implements-structure"></a>Implements-Struktur

Implementiert `QueryInterface` und `GetIid` für die angegebene Schnittstelle.

## <a name="syntax"></a>Syntax

```cpp
template <
   typename I0,
   typename I1 = Details::Nil,
   typename I2 = Details::Nil,
   typename I3 = Details::Nil,
   typename I4 = Details::Nil,
   typename I5 = Details::Nil,
   typename I6 = Details::Nil,
   typename I7 = Details::Nil,
   typename I8 = Details::Nil,
   typename I9 = Details::Nil
>
struct __declspec(novtable) Implements : Details::ImplementsHelper<RuntimeClassFlags<WinRt>, typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8, I9>::TypeT>, Details::ImplementsBase;
template <
   int flags,
   typename I0,
   typename I1,
   typename I2,
   typename I3,
   typename I4,
   typename I5,
   typename I6,
   typename I7,
   typename I8
>
struct __declspec(novtable) Implements<RuntimeClassFlags<flags>, I0, I1, I2, I3, I4, I5, I6, I7, I8> : Details::ImplementsHelper<RuntimeClassFlags<flags>, typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8>::TypeT>, Details::ImplementsBase;
```

### <a name="parameters"></a>Parameter

*I0*  
Die nullte Schnittstellen-ID. (Erforderlich)

*I1*  
Die erste Schnittstellen-ID. (Optional)

*I2*  
Die zweite Schnittstellen-ID. (Optional)

*I3*  
Die dritte Schnittstellen-ID. (Optional)

*I4*  
Die vierte Schnittstellen-ID. (Optional)

*I5*  
Die fünfte Schnittstellen-ID. (Optional)

*I6*  
Die sechste Schnittstellen-ID. (Optional)

*I7*  
Die siebte Schnittstellen-ID. (Optional)

*I8*  
Die achte Schnittstellen-ID. (Optional)

*I9*  
Die neunte Schnittstellen-ID. (Optional)

*flags*  
Von konfigurationsflags für die Klasse. Eine oder mehrere [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) Enumerationen, die im angegebenen ein [RuntimeClassFlags](../windows/runtimeclassflags-structure.md) Struktur.

## <a name="remarks"></a>Hinweise

Aus der Liste der angegebenen Schnittstellen abgeleitet und implementiert Helper-Vorlagen für `QueryInterface` und `GetIid`.

Jede *I0* über *I9* Schnittstellenparameter muss abgeleitet werden, entweder `IUnknown`, `IInspectable`, oder die [ChainInterfaces](../windows/chaininterfaces-structure.md) Vorlage. Die *Flags* Parameter bestimmt, ob die Unterstützung für generiert wird, `IUnknown` oder `IInspectable`.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

| Name        | Beschreibung                               |
| ----------- | ----------------------------------------- |
| `ClassFlags`| Ein Synonym für `RuntimeClassFlags<WinRt>`. |

### <a name="protected-methods"></a>Geschützte Methoden

| Name                                              | Beschreibung                                                                                                   |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| [Implements:: cancastto](#cancastto)               | Ruft einen Zeiger auf die angegebene Schnittstelle.                                                                    |
| [Implements:: casttounknown](#casttounknown)       | Ruft einen Zeiger auf die zugrunde liegende `IUnknown` Schnittstelle.                                                        |
| [Implements:: fillarraywithiid](#fillarraywithiid) | Fügt die Schnittstellen-ID, die durch den aktuellen nullten Vorlagenparameter angegeben wird, in das angegebene Array-Element. |

### <a name="protected-constants"></a>Geschützte Konstanten

| name                              | Beschreibung                                    |
| --------------------------------- | ---------------------------------------------- |
| [Implements:: iidcount](#iidcount) | Enthält die Anzahl von implementierten Schnittstellen-IDs. |

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`I0`

`ChainInterfaces`

`I0`

`ImplementsBase`

`ImplementsHelper`

`Implements`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="cancastto"></a>Implements:: cancastto

Ruft einen Zeiger auf die angegebene Schnittstelle.

```cpp
__forceinline HRESULT CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Parameter

*riid*  
Ein Verweis auf eine Schnittstellen-ID.

*ppv*  
Wenn erfolgreich, ein Zeiger auf die Schnittstelle durch angegeben *Riid*.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, der den Fehler, z.B. E_NOINTERFACE angibt.

### <a name="remarks"></a>Hinweise

Dies ist eine interne Hilfsmethode-Funktion, die einen QueryInterface-Vorgang ausführt.

## <a name="casttounknown"></a>Implements:: casttounknown

Ruft einen Zeiger auf die zugrunde liegende `IUnknown` Schnittstelle.

```cpp
__forceinline IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Rückgabewert

Dieser Vorgang immer erfolgreich ist, und gibt die `IUnknown` Zeiger.

### <a name="remarks"></a>Hinweise

Interne Hilfsmethode-Funktion.

## <a name="fillarraywithiid"></a>Implements:: fillarraywithiid

Fügt die Schnittstellen-ID, die durch den aktuellen nullten Vorlagenparameter angegeben wird, in das angegebene Array-Element.

```cpp
__forceinline static void FillArrayWithIid(
   unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Parameter

*index*  
Ein nullbasierter Index, der das Startelement "Array" für diesen Vorgang angibt. Klicken Sie nach Abschluss dieses Vorgangs *Index* um 1 erhöht.

*IIDs*  
Ein Array vom Typ IID.

### <a name="remarks"></a>Hinweise

Interne Hilfsmethode-Funktion.

## <a name="iidcount"></a>Implements:: iidcount

Enthält die Anzahl von implementierten Schnittstellen-IDs.

```cpp
static const unsigned long IidCount;
```
