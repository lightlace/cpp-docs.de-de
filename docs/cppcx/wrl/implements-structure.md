---
title: Implements-Struktur
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements
- implements/Microsoft::WRL::Implements::CanCastTo
- implements/Microsoft::WRL::Implements::CastToUnknown
- implements/Microsoft::WRL::Implements::FillArrayWithIid
- implements/Microsoft::WRL::Implements::IidCount
helpviewer_keywords:
- Microsoft::WRL::Implements structure
- Microsoft::WRL::Implements::CanCastTo method
- Microsoft::WRL::Implements::CastToUnknown method
- Microsoft::WRL::Implements::FillArrayWithIid method
- Microsoft::WRL::Implements::IidCount method
ms.assetid: 29b13e90-34d4-4a0b-babd-5187c9eb0c36
ms.openlocfilehash: 0ce6e9193107cbd0d033d99b257e41004b4343a8
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821856"
---
# <a name="implements-structure"></a>Implements-Struktur

Implementiert `QueryInterface` und `GetIid` für die angegebenen Schnittstellen.

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
struct __declspec(novtable) Implements :
    Details::ImplementsHelper<
        RuntimeClassFlags<WinRt>,
        typename Details::InterfaceListHelper<
            I0, I1, I2, I3, I4, I5, I6, I7, I8, I9
        >::TypeT
    >,
    Details::ImplementsBase;

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
struct __declspec(novtable) Implements<
        RuntimeClassFlags<flags>,
        I0, I1, I2, I3, I4, I5, I6, I7, I8> :
    Details::ImplementsHelper<
        RuntimeClassFlags<flags>,
        typename Details::InterfaceListHelper<
            I0, I1, I2, I3, I4, I5, I6, I7, I8
        >::TypeT
    >,
    Details::ImplementsBase;
```

### <a name="parameters"></a>Parameters

*I0*<br/>
Die nullte Schnittstellen-ID. (Erforderlich)

*I1*<br/>
Die erste Schnittstellen-ID. (Optional)

*I2*<br/>
Die zweite Schnittstellen-ID. (Optional)

*I3*<br/>
Die dritte Schnittstellen-ID. (Optional)

*I4*<br/>
Die vierte Schnittstellen-ID. (Optional)

*I5*<br/>
Die fünfte Schnittstellen-ID. (Optional)

*I6*<br/>
Die sechste Schnittstellen-ID. (Optional)

*I7*<br/>
Die siebte Schnittstellen-ID. (Optional)

*I8*<br/>
Die achte Schnittstellen-ID. (Optional)

*I9*<br/>
Die neunte Schnittstellen-ID. (Optional)

*flags*<br/>
Konfigurationsflags für die-Klasse. Mindestens eine [runtimeclasstype](runtimeclasstype-enumeration.md) -Enumeration, die in einer [runtimeclassflags](runtimeclassflags-structure.md) -Struktur angegeben ist.

## <a name="remarks"></a>Hinweise

Wird von der Liste der angegebenen Schnittstellen abgeleitet und implementiert hilfsvorlagen für `QueryInterface` und `GetIid`.

Jeder *I0* through *i9* -Schnittstellenparameter muss entweder von `IUnknown`, `IInspectable`oder der [chaininterfaces](chaininterfaces-structure.md) -Vorlage abgeleitet werden. Der *Flags* -Parameter bestimmt, ob die Unterstützung für `IUnknown` oder `IInspectable`generiert wird.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

| -Name        | Beschreibung                               |
| ----------- | ----------------------------------------- |
| `ClassFlags`| Ein Synonym für `RuntimeClassFlags<WinRt>`. |

### <a name="protected-methods"></a>Geschützte Methoden

| -Name                                              | Beschreibung                                                                                                   |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| [Implements::CanCastTo](#cancastto)               | Ruft einen Zeiger auf die angegebene-Schnittstelle ab.                                                                    |
| [Implementiert:: castto Unknown](#casttounknown)       | Ruft einen Zeiger auf die zugrunde liegende `IUnknown`-Schnittstelle ab.                                                        |
| [Implements::FillArrayWithIid](#fillarraywithiid) | Fügt die vom aktuellen nullte-Vorlagen Parameter angegebene Schnittstellen-ID in das angegebene Array Element ein. |

### <a name="protected-constants"></a>Geschützte Konstanten

| -Name                              | Beschreibung                                    |
| --------------------------------- | ---------------------------------------------- |
| [Implements::IidCount](#iidcount) | Enthält die Anzahl der implementierten Schnittstellen-IDs. |

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`I0`

`ChainInterfaces`

`I0`

`ImplementsBase`

`ImplementsHelper`

`Implements`

## <a name="requirements"></a>-Anforderungen

**Header:** implementiert. h

**Namespace:** Microsoft::WRL

## <a name="cancastto"></a>Implementiert:: CanCastTo

Ruft einen Zeiger auf die angegebene-Schnittstelle ab.

```cpp
__forceinline HRESULT CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Parameters

*riid*<br/>
Ein Verweis auf eine Schnittstellen-ID.

*ppv*<br/>
Wenn erfolgreich, ein Zeiger auf die durch *riid*angegebene Schnittstelle.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt, z. b. E_NOINTERFACE.

### <a name="remarks"></a>Hinweise

Dies ist eine interne Hilfsfunktion, die einen QueryInterface-Vorgang ausführt.

## <a name="casttounknown"></a>Implementiert:: castto Unknown

Ruft einen Zeiger auf die zugrunde liegende `IUnknown`-Schnittstelle ab.

```cpp
__forceinline IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Rückgabewert

Dieser Vorgang ist immer erfolgreich und gibt den `IUnknown` Zeiger zurück.

### <a name="remarks"></a>Hinweise

Interne Hilfsfunktion.

## <a name="fillarraywithiid"></a>Implements::FillArrayWithIid

Fügt die vom aktuellen nullte-Vorlagen Parameter angegebene Schnittstellen-ID in das angegebene Array Element ein.

```cpp
__forceinline static void FillArrayWithIid(
   unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Parameters

*index*<br/>
Ein NULL basierter Index, der das Start Array Element für diesen Vorgang angibt. Wenn dieser Vorgang abgeschlossen ist, wird der *Index* um 1 erhöht.

*IIDs*<br/>
Ein Array vom Typ IID.

### <a name="remarks"></a>Hinweise

Interne Hilfsfunktion.

## <a name="iidcount"></a>Implementiert:: iidcount

Enthält die Anzahl der implementierten Schnittstellen-IDs.

```cpp
static const unsigned long IidCount;
```
