---
title: Raw_method_prefix | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_method_prefix
dev_langs:
- C++
helpviewer_keywords:
- raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 78094053c963f5d836646e91857e171625c447c9
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808549"
---
# <a name="rawmethodprefix"></a>raw_method_prefix

**C++-spezifisch**

Gibt ein anderes Präfix an, um Namenskonflikte zu vermeiden.

## <a name="syntax"></a>Syntax

```
raw_method_prefix("Prefix")
```

### <a name="parameters"></a>Parameter

*Prefix*<br/>
Das zu verwendende Präfix.

## <a name="remarks"></a>Hinweise

Low-Level-Eigenschaften und Methoden sind verfügbar, durch die Memberfunktionen, die mit dem Namen, mit dem Standardpräfix **Raw_** so Namenskonflikte mit den allgemeinen Fehlerbehandlung Memberfunktionen zu vermeiden.

> [!NOTE]
> Die Auswirkungen der **Raw_method_prefix** Attribut wird nicht geändert werden, durch das Vorhandensein der [Raw_interfaces_only](#_predir_raw_interfaces_only) Attribut. Die **Raw_method_prefix** immer Vorrang `raw_interfaces_only` beim Angeben eines Präfix. Wenn beide Attribute, in der gleichen verwendet werden `#import` -Anweisung, und klicken Sie dann auf das Präfix, das gemäß der **Raw_method_prefix** Attribut wird verwendet.

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)