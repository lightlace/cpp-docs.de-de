---
title: raw_method_prefix
ms.date: 08/29/2019
f1_keywords:
- raw_method_prefix
helpviewer_keywords:
- raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
ms.openlocfilehash: b1bc536507716e5c117718ec825bf7fe76c84b61
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216147"
---
# <a name="raw_method_prefix"></a>raw_method_prefix

**C++Zugeschnitten**

Gibt ein anderes Präfix an, um Namenskonflikte zu vermeiden.

## <a name="syntax"></a>Syntax

> **#Import** *Typbibliothek* **raw_method_prefix (** "*prefix*" **)**

### <a name="parameters"></a>Parameter

*Vorsatz*\
Das zu verwendende Präfix.

## <a name="remarks"></a>Hinweise

Eigenschaften und Methoden auf niedriger Ebene werden von Element Funktionen mit dem Namen unter Verwendung eines Standard Präfixes von **Raw_** verfügbar gemacht, um Namenskonflikte mit den Funktionen für die Fehlerbehandlung auf hoher Ebene zu vermeiden.

> [!NOTE]
> Die Auswirkungen des **raw_method_prefix** -Attributs werden durch das vorhanden sein des [raw_interfaces_only](raw-interfaces-only.md) -Attributs unverändert. Der **raw_method_prefix** hat immer Vorrang `raw_interfaces_only` vor der Angabe eines Präfixes. Wenn beide Attribute in derselben `#import` Anweisung verwendet werden, wird das durch das **raw_method_prefix** -Attribut angegebene Präfix verwendet.

**End C++ -Specific**

## <a name="see-also"></a>Siehe auch

[#Import Attribute](../preprocessor/hash-import-attributes-cpp.md)\
[#Import-Direktive](../preprocessor/hash-import-directive-cpp.md)
