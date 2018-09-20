---
title: 'Argtraits:: args-Konstante | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraits::args
dev_langs:
- C++
helpviewer_keywords:
- args constant
ms.assetid: a68100ab-254b-4571-a0bc-946f1633a46b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 504909cba41588c0ccefccabfbd541a39d4327b2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387342"
---
# <a name="argtraitsargs-constant"></a>ArgTraits::args-Konstante

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
static const int args = -1; ;
```

## <a name="remarks"></a>Hinweise

Verfolgt die Anzahl von Parametern für die `Invoke` Methode einer Schnittstelle des Delegaten.

## <a name="remarks"></a>Hinweise

Wenn **Args** gleich-1 gibt an, es darf keine Übereinstimmung für die `Invoke` Methodensignatur.

## <a name="requirements"></a>Anforderungen

**Header:** event.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[ArgTraits-Struktur](../windows/argtraits-structure.md)<br/>
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)