---
title: Raw_property_prefixes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_property_prefixes
dev_langs:
- C++
helpviewer_keywords:
- raw_property_prefixes attribute
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1170440428a5c92e383152826827989d602e69fb
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808738"
---
# <a name="rawpropertyprefixes"></a>raw_property_prefixes

**C++-spezifisch**

Gibt alternative Präfixe für drei Eigenschaftenmethoden an.

## <a name="syntax"></a>Syntax

```
raw_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")
```

### <a name="parameters"></a>Parameter

*GetPrefix*<br/>
Präfix für zu verwendende der `propget` Methoden.

*PutPrefix*<br/>
Präfix für zu verwendende der `propput` Methoden.

*PutRefPrefix*<br/>
Präfix für zu verwendende der `propputref` Methoden.

## <a name="remarks"></a>Hinweise

In der Standardeinstellung auf niedriger Ebene `propget`, `propput`, und `propputref` Methoden von Namen mit Präfixen von Memberfunktionen verfügbar gemacht werden **Get_**, **Put_**, und **Putref_** bzw. Diese Präfixe sind kompatibel mit den Namen, die in den Headerdateien verwendet werden, die von MIDL generiert werden.

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)