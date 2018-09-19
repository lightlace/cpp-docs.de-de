---
title: ArgTraits-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraits
dev_langs:
- C++
helpviewer_keywords:
- ArgTraits structure
ms.assetid: 58ae4115-c1bc-48c8-b01b-e60554841c30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e3eade86404bcd4fef7ce3356d36a43ac6a59a8f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42597754"
---
# <a name="argtraits-structure"></a>ArgTraits-Struktur

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template<typename TMemberFunction>
struct ArgTraits;
template<typename TDelegateInterface>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(void)>;
template<
   typename TDelegateInterface,
   typename TArg1
>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1)>;
template<
   typename TDelegateInterface,
   typename TArg1,
   typename TArg2
>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2)>;
template<
   typename TDelegateInterface,
   typename TArg1,
   typename TArg2,
   typename TArg3
>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3)>;
template<
   typename TDelegateInterface,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4
>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4)>;
template<
   typename TDelegateInterface,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5
>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5)>;
template<
   typename TDelegateInterface,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6
>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6)>;
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
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7)>;
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
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8)>;
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
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8, TArg9)>;
```

### <a name="parameters"></a>Parameter

*TMemberFunction*  
TypeName-Parameter für eine ArgTraits-Struktur, die einer entsprechen, kann keine `Invoke` Methodensignatur.

*TDelegateInterface*  
Ein Delegat-Schnittstelle.

*TArg1*  
Der Typ, der das erste Argument von der `Invoke` Methode.

*TArg2*  
Der Typ des zweiten Arguments des der `Invoke` Methode.

*TArg3*  
Der Typ des dritten Arguments der der `Invoke` Methode.

*TArg4*  
Der Typ des vierten Arguments der der `Invoke` Methode.

*TArg5*  
Der Typ des fünften Arguments der der `Invoke` Methode.

*TArg6*  
Der Typ des sechsten Arguments der der `Invoke` Methode.

*TArg7*  
Der Typ des siebten Arguments der der `Invoke` Methode.

*TArg8*  
Der Typ des Arguments achte der `Invoke` Methode.

*TArg9*  
Der Typ des neunten Arguments der der `Invoke` Methode.

## <a name="remarks"></a>Hinweise

Die **ArgTraits** Struktur deklariert einen Delegaten angegebenen Schnittstelle und eine anonyme Memberfunktion, die eine angegebene Anzahl von Parametern.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`Arg1Type`|Die Typedef für TArg1.|
|`Arg2Type`|Die Typedef für TArg2.|
|`Arg3Type`|Die Typedef für TArg3.|
|`Arg4Type`|Die Typedef für TArg4.|
|`Arg5Type`|Die Typedef für TArg5.|
|`Arg6Type`|Die Typedef für TArg6.|
|`Arg7Type`|Die Typedef für TArg7.|
|`Arg8Type`|Die Typedef für TArg8.|
|`Arg9Type`|Die Typedef für TArg9.|

### <a name="public-constants"></a>Öffentliche Konstanten

|name|Beschreibung|
|----------|-----------------|
|[ArgTraits::args-Konstante](../windows/argtraits-args-constant.md)|Verfolgt die Anzahl von Parametern für die `Invoke` Methode einer Schnittstelle des Delegaten.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ArgTraits`

## <a name="requirements"></a>Anforderungen

**Header:** event.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)