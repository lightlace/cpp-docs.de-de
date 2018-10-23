---
title: Rename_search_namespace | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- rename_search_namespace
dev_langs:
- C++
helpviewer_keywords:
- rename_search_namespace attribute
ms.assetid: 47c9d7fd-59dc-4c62-87a1-9011a0040167
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f0cc95851c4aa7127e690ec013b9d06d57f2730d
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808887"
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