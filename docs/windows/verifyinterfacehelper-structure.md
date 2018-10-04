---
title: VerifyInterfaceHelper-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInterfaceHelper
- implements/Microsoft::WRL::Details::VerifyInterfaceHelper::Verify
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::VerifyInterfaceHelper structure
- Microsoft::WRL::Details::VerifyInterfaceHelper::Verify method
ms.assetid: ea95b641-199a-4fdf-964b-186b40cb3ba7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b70155566695ade6b6778ade3b4758faebb3ea67
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788864"
---
# <a name="verifyinterfacehelper-structure"></a>VerifyInterfaceHelper-Struktur

Unterstützt die Windows Runtime C++ Template Library-Infrastruktur, und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template <bool isWinRTInterface, typename I>
struct VerifyInterfaceHelper;

template <typename I>
struct VerifyInterfaceHelper<false, I>;
```

### <a name="parameters"></a>Parameter

*I*<br/>
Eine Schnittstelle, um zu überprüfen.

*isWinRTInterface*

## <a name="remarks"></a>Hinweise

Überprüft, ob die die Template-Parameter angegebene Schnittstelle bestimmte Anforderungen erfüllt.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

Name                                            | Beschreibung
----------------------------------------------- | ---------------------------------------------------------------------------------------------------
[VerifyInterfaceHelper::Verify-Methode](#verify) | Überprüft, ob die Schnittstelle, die durch den aktuellen Vorlagenparameter angegeben bestimmte Anforderungen erfüllt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`VerifyInterfaceHelper`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="verify"></a>Verifyinterfacehelper:: Verify

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
static void Verify();
```

### <a name="remarks"></a>Hinweise

Überprüft, ob die Schnittstelle, die durch den aktuellen Vorlagenparameter angegeben bestimmte Anforderungen erfüllt.
