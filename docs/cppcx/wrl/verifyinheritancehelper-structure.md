---
title: VerifyInheritanceHelper-Struktur
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper::Verify
helpviewer_keywords:
- Microsoft::WRL::Details::VerifyInheritanceHelper structure
- Microsoft::WRL::Details::VerifyInheritanceHelper::Verify method
ms.assetid: 8a48a702-0f71-4807-935b-8311f0a7a8b6
ms.openlocfilehash: c37a0eb74fd65b3d349d5b8b7c792fbaf7d1ac9a
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58784238"
---
# <a name="verifyinheritancehelper-structure"></a>VerifyInheritanceHelper-Struktur

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template <typename I, typename Base>
struct VerifyInheritanceHelper;

template <typename I>
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
[VerifyInheritanceHelper::Verify](#verify) | Testet die beiden Schnittstellen, die durch die aktuellen Vorlagenparameter angegeben, und bestimmt, ob eine Schnittstelle von der anderen abgeleitet ist.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`VerifyInheritanceHelper`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="verify"></a>VerifyInheritanceHelper::Verify

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
static void Verify();
```

### <a name="remarks"></a>Hinweise

Testet die beiden Schnittstellen, die durch die aktuellen Vorlagenparameter angegeben, und bestimmt, ob eine Schnittstelle von der anderen abgeleitet ist.

Ein Fehler wird ausgegeben, wenn eine Schnittstelle nicht von der anderen abgeleitet ist.
