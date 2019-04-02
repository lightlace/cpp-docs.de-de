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
ms.openlocfilehash: 17109508cf99888ccde79be39a41c5361da24c6e
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785233"
---
# <a name="argtraits-structure"></a>ArgTraits-Struktur

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

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

### <a name="parameters"></a>Parameter

*TMemberFunction*<br/>
TypeName-Parameter für eine ArgTraits-Struktur, die einer entsprechen, kann keine `Invoke` Methodensignatur.

*TDelegateInterface*<br/>
Ein Delegat-Schnittstelle.

*TArg1*<br/>
Der Typ, der das erste Argument von der `Invoke` Methode.

*TArg2*<br/>
Der Typ des zweiten Arguments des der `Invoke` Methode.

*TArg3*<br/>
Der Typ des dritten Arguments der der `Invoke` Methode.

*TArg4*<br/>
Der Typ des vierten Arguments der der `Invoke` Methode.

*TArg5*<br/>
Der Typ des fünften Arguments der der `Invoke` Methode.

*TArg6*<br/>
Der Typ des sechsten Arguments der der `Invoke` Methode.

*TArg7*<br/>
Der Typ des siebten Arguments der der `Invoke` Methode.

*TArg8*<br/>
Der Typ des Arguments achte der `Invoke` Methode.

*TArg9*<br/>
Der Typ des neunten Arguments der der `Invoke` Methode.

## <a name="remarks"></a>Hinweise

Die `ArgTraits` Struktur deklariert einen Delegaten angegebenen Schnittstelle und eine anonyme Memberfunktion, die eine angegebene Anzahl von Parametern.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

Name       | Beschreibung
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

Name                     | Beschreibung
------------------------ | ---------------------------------------------------------------------------------------
[ArgTraits::args](#args) | Verfolgt die Anzahl von Parametern für die `Invoke` Methode einer Schnittstelle des Delegaten.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ArgTraits`

## <a name="requirements"></a>Anforderungen

**Header:** event.h

**Namespace:** Microsoft::WRL::Details

## <a name="args"></a>ArgTraits::args

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
static const int args = -1;
```

### <a name="remarks"></a>Hinweise

Verfolgt die Anzahl von Parametern für die `Invoke` Methode einer Schnittstelle des Delegaten. Wenn `args` gleich-1 ist, es darf keine Übereinstimmung für die `Invoke` Methodensignatur.
