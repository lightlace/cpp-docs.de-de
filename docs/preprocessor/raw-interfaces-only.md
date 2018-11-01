---
title: raw_interfaces_only
ms.date: 11/04/2016
f1_keywords:
- raw_interfaces_only
helpviewer_keywords:
- raw_interfaces_only attribute
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
ms.openlocfilehash: c07401036261b9f93bb2c07dcf3aff1ecf72e2fc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519352"
---
# <a name="rawinterfacesonly"></a>raw_interfaces_only
**C++-spezifisch**

Unterdrückt die Generierung von Fehlerbehandlungs Wrapperfunktionen und [Eigenschaft](../cpp/property-cpp.md) Deklarationen, die diese Wrapperfunktionen verwenden.

## <a name="syntax"></a>Syntax

```
raw_interfaces_only
```

## <a name="remarks"></a>Hinweise

Die **Raw_interfaces_only** -Attribut bewirkt auch, dass das Standardpräfix verwendet wird, benennen Sie die Funktionen ohne Eigenschaft entfernt werden soll. Normalerweise ist das Präfix ist **Raw_**. Wenn dieses Attribut festgelegt wird, stammen die Funktionsnamen direkt aus der Typbibliothek.

Dieses Attribut ermöglicht, dass Sie nur die Inhalte auf niedriger Ebene aus der Typbibliothek verfügbar machen.

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)