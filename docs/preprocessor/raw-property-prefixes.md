---
title: raw_property_prefixes-Attribut importieren
ms.date: 08/29/2019
f1_keywords:
- raw_property_prefixes
helpviewer_keywords:
- raw_property_prefixes attribute
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
ms.openlocfilehash: d4d91470781e7c5f673fd228c24904322d1db8b3
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216039"
---
# <a name="raw_property_prefixes-import-attribute"></a>raw_property_prefixes-Attribut importieren

**C++Zugeschnitten**

Gibt alternative Präfixe für drei Eigenschaftenmethoden an.

## <a name="syntax"></a>Syntax

> **#Import** *Typbibliothek* **raw_property_prefixes (** "*getprefix*" **,** "*putprefix*" **,** "*PutRef Prefix*" **)**

### <a name="parameters"></a>Parameter

*Getprefix*\
Präfix, das für `propget` die Methoden verwendet werden soll.

*Putprefix*\
Präfix, das für `propput` die Methoden verwendet werden soll.

*PutRef-Präfix*\
Präfix, das für `propputref` die Methoden verwendet werden soll.

## <a name="remarks"></a>Hinweise

Standardmäßig werden Low-Level `propget`- `propput`,- `propputref` und-Methoden `get_`von Element Funktionen verfügbar gemacht, die mit dem `put_`Präfix `putref_`, bzw. benannt werden. Diese Präfixe sind kompatibel mit den Namen, die in den Headerdateien verwendet werden, die von MIDL generiert werden.

**End C++ -Specific**

## <a name="see-also"></a>Siehe auch

[#Import Attribute](../preprocessor/hash-import-attributes-cpp.md)\
[#Import-Direktive](../preprocessor/hash-import-directive-cpp.md)
