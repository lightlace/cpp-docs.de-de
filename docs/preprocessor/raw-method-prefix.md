---
title: raw_method_prefix
ms.date: 10/18/2018
f1_keywords:
- raw_method_prefix
helpviewer_keywords:
- raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
ms.openlocfilehash: 4169b4e23049bf1cf2c61eaefba619169e0ce377
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50467764"
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