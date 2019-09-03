---
title: raw_interfaces_only-Attribut importieren
ms.date: 08/29/2019
f1_keywords:
- raw_interfaces_only
helpviewer_keywords:
- raw_interfaces_only attribute
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
ms.openlocfilehash: 4b79aa4dbafa204d84f4d6ed7ec78fdec1b81fa7
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216205"
---
# <a name="raw_interfaces_only-import-attribute"></a>raw_interfaces_only-Attribut importieren

**C++Zugeschnitten**

Unterdrückt die Generierung von Wrapper Funktionen für die Fehlerbehandlung und [Eigenschafts](../cpp/property-cpp.md) Deklarationen, die diese Wrapper Funktionen verwenden.

## <a name="syntax"></a>Syntax

> **#Import** *Typbibliothek* **raw_interfaces_only**

## <a name="remarks"></a>Hinweise

Das **raw_interfaces_only** -Attribut bewirkt auch, dass das Standard Präfix, das beim Benennen der nicht-Eigenschafts Funktionen verwendet wird, entfernt wird. Normalerweise ist `raw_`das Präfix. Wenn dieses Attribut angegeben wird, werden die Funktionsnamen direkt aus der Typbibliothek entnommen.

Dieses Attribut ermöglicht, dass Sie nur die Inhalte auf niedriger Ebene aus der Typbibliothek verfügbar machen.

**End C++ -Specific**

## <a name="see-also"></a>Siehe auch

[#Import Attribute](../preprocessor/hash-import-attributes-cpp.md)\
[#Import-Direktive](../preprocessor/hash-import-directive-cpp.md)
