---
title: ArgTraits-Struktur
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraits
- event/Microsoft::WRL::Details::ArgTraits::args
helpviewer_keywords:
- Microsoft::WRL::Details::ArgTraits structure
- Microsoft::WRL::Details::ArgTraits::args constant
ms.assetid: 58ae4115-c1bc-48c8-b01b-e60554841c30
ms.openlocfilehash: c13e7fec3289b66b40e44f91404a50cba7a473b1
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821713"
---
# <a name="argtraits-structure"></a>ArgTraits-Struktur

Unterstützt die WRL-Infrastruktur und ist nicht für die direkte Verwendung im Code vorgesehen.

## <a name="syntax"></a>Syntax

```cpp
template<typename TMemberFunction>
struct ArgTraits;

template<typename TDelegateInterface>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(void)>;

template<typename TDelegateInterface, typename TArg1>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1)>;

template<typename TDelegateInterface, typename TArg1, typename TArg2>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7,
    typename TArg8
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7,
    typename TArg8,
    typename TArg9
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8, TArg9)>;
```

### <a name="parameters"></a>Parameters

*Tmembership-Funktion*<br/>
Typname-Parameter für eine argtrait-Struktur, die keiner `Invoke` Methoden Signatur entsprechen kann.

*TDelegateInterface*<br/>
Eine delegatschnittstelle.

*TArg1*<br/>
Der Typ des ersten Arguments der `Invoke` Methode.

*TArg2*<br/>
Der Typ des zweiten Arguments der `Invoke` Methode.

*TArg3*<br/>
Der Typ des dritten Arguments der `Invoke` Methode.

*TArg4*<br/>
Der Typ des vierten Arguments der `Invoke` Methode.

*TArg5*<br/>
Der Typ des fünften Arguments der `Invoke` Methode.

*TArg6*<br/>
Der Typ des sechsten Arguments der `Invoke` Methode.

*TArg7*<br/>
Der Typ des siebten Arguments der `Invoke` Methode.

*TArg8*<br/>
Der Typ des achten Arguments der `Invoke` Methode.

*TArg9*<br/>
Der Typ des neunten Arguments der `Invoke` Methode.

## <a name="remarks"></a>Hinweise

Die `ArgTraits`-Struktur deklariert eine angegebene delegatschnittstelle und eine anonyme Member-Funktion, die über eine angegebene Anzahl von Parametern verfügt.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

-Name       | Beschreibung
---------- | ----------------------
`Arg1Type` | Die Typedef für TArg1.
`Arg2Type` | Die Typedef für TArg2.
`Arg3Type` | Die Typedef für TArg3.
`Arg4Type` | Die Typedef für TArg4.
`Arg5Type` | Die Typedef für TArg5.
`Arg6Type` | Die Typedef für TArg6.
`Arg7Type` | Die Typedef für TArg7.
`Arg8Type` | Die Typedef für TArg8.
`Arg9Type` | Die Typedef für TArg9.

### <a name="public-constants"></a>Öffentliche Konstanten

-Name                     | Beschreibung
------------------------ | ---------------------------------------------------------------------------------------
[ArgTraits::args](#args) | Gibt die Anzahl der Parameter für die `Invoke`-Methode einer delegatschnittstelle an.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ArgTraits`

## <a name="requirements"></a>-Anforderungen

**Header:** Event. h

**Namespace:** Microsoft:: WRL::D etails

## <a name="args"></a>ArgTraits::args

Unterstützt die WRL-Infrastruktur und ist nicht für die direkte Verwendung im Code vorgesehen.

```cpp
static const int args = -1;
```

### <a name="remarks"></a>Hinweise

Gibt die Anzahl der Parameter für die `Invoke`-Methode einer delegatschnittstelle an. Wenn `args` gleich-1 ist, kann die Signatur der `Invoke` Methode nicht gefunden werden.
