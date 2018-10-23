---
title: Rename_namespace | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- rename_namespace
dev_langs:
- C++
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 966c6dda7e5e0bd28e78f37967397c3b64e4e55c
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808471"
---
# <a name="renamenamespace"></a>rename_namespace

**C++-spezifisch**

Benennt den Namespace, der die Inhalte der Typbibliothek enthält, um.

## <a name="syntax"></a>Syntax

```
rename_namespace("NewName")
```

### <a name="parameters"></a>Parameter

*Neuer Name*<br/>
Der neue Name des neuen Namespace.

## <a name="remarks"></a>Hinweise

Es dauert ein einzelnes Argument, *NewName*, die den neuen Namen für den Namespace angibt.

Verwenden Sie zum Entfernen des Namespaces der [No_namespace](../preprocessor/no-namespace.md) Attribut.

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)