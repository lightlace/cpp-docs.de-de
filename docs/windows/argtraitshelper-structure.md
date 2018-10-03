---
title: ArgTraitsHelper-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/21/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraitsHelper
- event/Microsoft::WRL::Details::ArgTraitsHelper::args
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::ArgTraitsHelper structure
- Microsoft::WRL::Details::ArgTraitsHelper::args constant
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b608f5da893019d7700891968dcdc06489c563ea
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234228"
---
# <a name="argtraitshelper-structure"></a>ArgTraitsHelper-Struktur

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template<typename TDelegateInterface>
struct ArgTraitsHelper;
```

### <a name="parameters"></a>Parameter

*TDelegateInterface*<br/>
Ein Delegat-Schnittstelle.

## <a name="remarks"></a>Hinweise

Hilft, die gemeinsamen Merkmale der Argumente des Delegaten definieren.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

Name         | Beschreibung
------------ | ------------------------------------------------------
`methodType` | Ein Synonym für `decltype(&TDelegateInterface::Invoke)`.
`Traits`     | Ein Synonym für `ArgTraits<methodType>`.

### <a name="public-constants"></a>Öffentliche Konstanten

name                           | Beschreibung
------------------------------ | ---------------------------------------------------------------------------------------------------------------------
[Argtraitshelper:: args](#args) | Hilft [argtraits:: args](#args) behalten Sie die Anzahl der Parameter der `Invoke` Methode einer Schnittstelle des Delegaten.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ArgTraitsHelper`

## <a name="requirements"></a>Anforderungen

**Header:** event.h

**Namespace:** Microsoft::WRL::Details

## <a name="args"></a>Argtraitshelper:: args

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
static const int args = Traits::args;
```

### <a name="remarks"></a>Hinweise

Hilft `ArgTraitsHelper::args` behalten Sie die Anzahl der Parameter der `Invoke` Methode einer Schnittstelle des Delegaten.
