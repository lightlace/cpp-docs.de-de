---
title: high_property_prefixes-Attribut importieren
ms.date: 08/29/2019
f1_keywords:
- high_property_prefixes
helpviewer_keywords:
- high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
ms.openlocfilehash: 9e44f6f1afae479f803f4c6d866ef3ee38744561
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219001"
---
# <a name="high_property_prefixes-import-attribute"></a>high_property_prefixes-Attribut importieren

**C++Zugeschnitten**

Gibt alternative Präfixe für drei Eigenschaftenmethoden an.

## <a name="syntax"></a>Syntax

> **#Import** *Typbibliothek* **high_property_prefixes (** "*getprefix*" **,** "*putprefix*" **,** "*PutRef Prefix*" **)**

### <a name="parameters"></a>Parameter

*Getprefix*\
Präfix, das für die `propget` Methoden verwendet werden soll.

*Putprefix*\
Präfix, das für die `propput` Methoden verwendet werden soll.

*PutRef-Präfix*\
Präfix, das für die `propputref` Methoden verwendet werden soll.

## <a name="remarks"></a>Hinweise

Standard `propget`mäßig werden `propputref` Methoden zur Fehlerbehandlung `propput`auf hoher Ebene durch Element `PutRef`Funktionen mit den Präfixen `Get`, `Put`bzw. verfügbar gemacht.

**End C++ -Specific**

## <a name="see-also"></a>Siehe auch

[#Import Attribute](../preprocessor/hash-import-attributes-cpp.md)\
[#Import-Direktive](../preprocessor/hash-import-directive-cpp.md)
