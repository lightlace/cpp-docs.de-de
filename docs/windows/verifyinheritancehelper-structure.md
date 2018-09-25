---
title: VerifyInheritanceHelper-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/24/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper::Verify
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::VerifyInheritanceHelper structure
- Microsoft::WRL::Details::VerifyInheritanceHelper::Verify method
ms.assetid: 8a48a702-0f71-4807-935b-8311f0a7a8b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6231345b837cae8f36e8441173300d804c0ea167
ms.sourcegitcommit: edb46b0239a0e616af4ec58906e12338c3e8d2c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47169632"
---
# <a name="verifyinheritancehelper-structure"></a>VerifyInheritanceHelper-Struktur

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template <
   typename I,
   typename Base
>
struct VerifyInheritanceHelper;
template <
   typename I
>
struct VerifyInheritanceHelper<I, Nil>;
```

### <a name="parameters"></a>Parameter

*I*<br/>
Ein Typ.

*Basis*<br/>
Einen anderen Typ.

## <a name="remarks"></a>Hinweise

Testet, ob eine Schnittstelle, die von einer anderen Schnittstelle abgeleitet wird.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

Name                                       | Beschreibung
------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------
[Verifyinheritancehelper:: Verify](#verify) | Testet die beiden Schnittstellen, die durch die aktuellen Vorlagenparameter angegeben, und bestimmt, ob eine Schnittstelle von der anderen abgeleitet ist.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`VerifyInheritanceHelper`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="verify"></a>Verifyinheritancehelper:: Verify

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
static void Verify();
```

### <a name="remarks"></a>Hinweise

Testet die beiden Schnittstellen, die durch die aktuellen Vorlagenparameter angegeben, und bestimmt, ob eine Schnittstelle von der anderen abgeleitet ist.

Ein Fehler wird ausgegeben, wenn eine Schnittstelle nicht von der anderen abgeleitet ist.
