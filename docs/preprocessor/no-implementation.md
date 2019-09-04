---
title: no_implementation-Attribut importieren
ms.date: 08/29/2019
f1_keywords:
- no_implementation
helpviewer_keywords:
- no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
ms.openlocfilehash: 8f0a7454fdbedc1959b665ccb2a23748d21c342d
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220772"
---
# <a name="no_implementation-import-attribute"></a>no_implementation-Attribut importieren

**C++Zugeschnitten**

Unterdrückt die Generierung des `.tli` Headers, der die Implementierungen der Wrapper Element Funktionen enthält.

## <a name="syntax"></a>Syntax

> **#Import** *Typbibliothek* **no_implementation**

## <a name="remarks"></a>Hinweise

Wenn dieses Attribut angegeben wird, wird `.tlh` der-Header mit den-Deklarationen, die Typbibliotheks Elemente verfügbar machen, ohne `#include` eine-Anweisung zum `.tli` einschließen der Header Datei generiert.

Dieses Attribut wird zusammen mit [implementation_only](../preprocessor/implementation-only.md)verwendet.

**End C++ -Specific**

## <a name="see-also"></a>Siehe auch

[#Import Attribute](../preprocessor/hash-import-attributes-cpp.md)\
[#Import-Direktive](../preprocessor/hash-import-directive-cpp.md)
