---
title: rename_search_namespace
ms.date: 10/18/2018
f1_keywords:
- rename_search_namespace
helpviewer_keywords:
- rename_search_namespace attribute
ms.assetid: 47c9d7fd-59dc-4c62-87a1-9011a0040167
ms.openlocfilehash: 1e8d682b3d52c80779d62443074614480ed514ee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50510733"
---
# <a name="renamesearchnamespace"></a>rename_search_namespace

**C++-spezifisch**

Hat die gleiche Funktionalität wie die [Rename_namespace](../preprocessor/rename-namespace.md) Attribut wird aber verwendet in Typbibliotheken, die Sie verwenden die `#import` -Direktive zusammen mit der [Auto_search](../preprocessor/auto-search.md) Attribut.

## <a name="syntax"></a>Syntax

```
rename_search_namespace("NewName")
```

### <a name="parameters"></a>Parameter

*Neuer Name*<br/>
Der neue Name des neuen Namespace.

## <a name="remarks"></a>Hinweise

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)