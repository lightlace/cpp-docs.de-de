---
title: InspectableClass-Makro
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::InspectableClass
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
ms.openlocfilehash: ee2a76edb967923a03ce6720b4163baf1cc48c32
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500476"
---
# <a name="inspectableclass-macro"></a>InspectableClass-Makro

Legt den Ablaufklassennamen und die Vertrauensebene fest.

## <a name="syntax"></a>Syntax

```cpp
InspectableClass(
   runtimeClassName,
   trustLevel)
```

### <a name="parameters"></a>Parameter

*runtimeClassName*<br/>
Der vollständige wörtliche Name der Laufzeitklasse.

*trustLevel*<br/>
Einer der [Trust Level](/windows/win32/api/inspectable/ne-inspectable-trustlevel) -Enumerationswerte.

## <a name="remarks"></a>Hinweise

Das **inspectableclass** -Makro kann nur mit Windows-Runtime Typen verwendet werden.

## <a name="requirements"></a>Anforderungen

**Header:** implementiert. h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[RuntimeClass-Klasse](runtimeclass-class.md)