---
title: InspectableClass-Makro
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::InspectableClass
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
ms.openlocfilehash: 9d194f5a87ac4a142301bc896cb3ed172f119473
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59025710"
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
Eines der [TrustLevel](/windows/desktop/api/inspectable/ne-inspectable-trustlevel) aufgelistete Werte bereitstellen.

## <a name="remarks"></a>Hinweise

Die **InspectableClass** Makro kann nur mit Windows-Runtime-Typen verwendet werden.

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[RuntimeClass-Klasse](runtimeclass-class.md)