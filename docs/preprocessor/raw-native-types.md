---
title: raw_native_types
ms.date: 11/04/2016
f1_keywords:
- raw_native_types
helpviewer_keywords:
- raw_native_types attribute
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
ms.openlocfilehash: e48aa2ca1469d38b67dcb06a3377713141a158e6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620440"
---
# <a name="rawnativetypes"></a>raw_native_types
**C++-spezifisch**

Deaktiviert die Verwendung COM-Unterstützungsklassen in den Wrapperfunktionen auf hoher Ebene und erzwingt stattdessen die Verwendung von Datentypen auf niedriger Ebene.

## <a name="syntax"></a>Syntax

```
raw_native_types
```

## <a name="remarks"></a>Hinweise

Standardmäßig verwenden die Fehlerbehandlungsmethoden auf hoher Ebene die COM-Unterstützungsklassen [_bstr_t](../cpp/bstr-t-class.md) und [_variant_t](../cpp/variant-t-class.md) anstelle von der `BSTR` und `VARIANT` -Datentypen und unformatierten COM-Schnittstellenzeigern. Diese Klassen kapseln die Details der Zuordnung und Freigabe des Arbeitsspeichers für diese Datentypen und vereinfachen die Typumwandlungs- und Konvertierungsoperationen erheblich.

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)