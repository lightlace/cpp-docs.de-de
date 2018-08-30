---
title: InspectableClass-Makro | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::InspectableClass
dev_langs:
- C++
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9b85a10c68b7379f0e59bf859b3d8badf7413195
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43208340"
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

*runtimeClassName*  
Der vollständige wörtliche Name der Laufzeitklasse.

*trustLevel*  
Eines der [TrustLevel](https://msdn.microsoft.com/library/br224625.aspx) aufgelistete Werte bereitstellen.

## <a name="remarks"></a>Hinweise

Die **InspectableClass** Makro kann nur mit Windows-Runtime-Typen verwendet werden.

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[RuntimeClass-Klasse](../windows/runtimeclass-class.md)