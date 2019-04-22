---
title: rename_search_namespace
ms.date: 10/18/2018
f1_keywords:
- rename_search_namespace
helpviewer_keywords:
- rename_search_namespace attribute
ms.assetid: 47c9d7fd-59dc-4c62-87a1-9011a0040167
ms.openlocfilehash: ca5d24ca9cc12e9defaa395cf150bc3c04ee4439
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59022852"
---
# <a name="renamesearchnamespace"></a>rename_search_namespace

**C++-spezifisch**

Hat die gleiche Funktionalität wie die [Rename_namespace](../preprocessor/rename-namespace.md) Attribut wird aber verwendet in Typbibliotheken, die Sie verwenden die `#import` -Direktive zusammen mit der [Auto_search](../preprocessor/auto-search.md) Attribut.

## <a name="syntax"></a>Syntax

```
rename_search_namespace("NewName")
```

### <a name="parameters"></a>Parameter

*NewName*<br/>
Der neue Name des neuen Namespace.

## <a name="remarks"></a>Hinweise

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)