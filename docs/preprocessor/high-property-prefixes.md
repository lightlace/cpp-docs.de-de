---
title: high_property_prefixes
ms.date: 10/18/2018
f1_keywords:
- high_property_prefixes
helpviewer_keywords:
- high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
ms.openlocfilehash: 3f8975ec9737e02bb1216166cc6c241549e95a07
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029368"
---
# <a name="highpropertyprefixes"></a>high_property_prefixes

**C++-spezifisch**

Gibt alternative Präfixe für drei Eigenschaftenmethoden an.

## <a name="syntax"></a>Syntax

```
high_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")
```

### <a name="parameters"></a>Parameter

*GetPrefix*<br/>
Präfix für zu verwendende der `propget` Methoden.

*PutPrefix*<br/>
Präfix für zu verwendende der `propput` Methoden.

*PutRefPrefix*<br/>
Präfix für zu verwendende der `propputref` Methoden.

## <a name="remarks"></a>Hinweise

In der Standardeinstellung auf hoher Ebene für die Fehlerbehandlung `propget`, `propput`, und `propputref` Methoden verfügbar gemacht werden, durch die Memberfunktionen, die mit dem Namen mit Präfixen `Get`, `Put`, und `PutRef`bzw.

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)