---
title: raw_native_types
ms.date: 11/04/2016
f1_keywords:
- raw_native_types
helpviewer_keywords:
- raw_native_types attribute
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
ms.openlocfilehash: 32b77905ef7025334e5101e76864da9a15c50cf6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180478"
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