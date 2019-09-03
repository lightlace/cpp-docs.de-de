---
title: raw_native_types-Attribut importieren
ms.date: 08/29/2019
f1_keywords:
- raw_native_types
helpviewer_keywords:
- raw_native_types attribute
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
ms.openlocfilehash: eb08a8e7cb081bd7a470c3c1ecf1492a7a65f833
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216068"
---
# <a name="raw_native_types-import-attribute"></a>raw_native_types-Attribut importieren

**C++Zugeschnitten**

Deaktiviert die Verwendung von com-Unterstützungs Klassen in den Wrapper Funktionen auf hoher Ebene und erzwingt stattdessen die Verwendung von Datentypen auf niedriger Ebene.

## <a name="syntax"></a>Syntax

> **#Import** *Typbibliothek* **raw_native_types**

## <a name="remarks"></a>Hinweise

Standardmäßig verwenden die Methoden für die Fehlerbehandlung auf hoher Ebene die com-Unterstützungs Klassen [_bstr_t](../cpp/bstr-t-class.md) und [_variant_t](../cpp/variant-t-class.md) `BSTR` anstelle der Datentypen `VARIANT` und und der unformatierten COM-Schnittstellen Zeiger. Diese Klassen kapseln die Details der Zuordnung und Freigabe des Arbeitsspeichers für diese Datentypen und vereinfachen die Typumwandlungs- und Konvertierungsoperationen erheblich.

**End C++ -Specific**

## <a name="see-also"></a>Siehe auch

[#Import Attribute](../preprocessor/hash-import-attributes-cpp.md)\
[#Import-Direktive](../preprocessor/hash-import-directive-cpp.md)
