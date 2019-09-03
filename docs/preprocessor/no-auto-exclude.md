---
title: no_auto_exclude-Attribut importieren
ms.date: 08/29/2019
f1_keywords:
- no_auto_exclude
helpviewer_keywords:
- no_auto_exclude attribute
ms.assetid: 3241ef9c-758a-4e86-bdc5-37da6072430f
ms.openlocfilehash: 530c2b2adf24e964cb0a512371f4430a61bf8b11
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216077"
---
# <a name="no_auto_exclude-import-attribute"></a>no_auto_exclude-Attribut importieren

**C++Zugeschnitten**

Deaktiviert den automatische Ausschluss.

## <a name="syntax"></a>Syntax

> **#Import** *Typbibliothek* **no_auto_exclude**

## <a name="remarks"></a>Hinweise

Typbibliotheken können Definitionen der Elemente enthalten, die in Systemheadern oder anderen Typbibliotheken definiert sind. `#import` versucht, mehrfache Definitionsfehler dadurch zu vermeiden, dass solche Elemente automatisch ausgeschlossen werden. Dadurch wird die Compilerwarnung [(Stufe 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md) für jedes auszuschließende Element ausgegeben. Sie können den automatischen Ausschluss mithilfe dieses Attributs deaktivieren.

**End C++ -Specific**

## <a name="see-also"></a>Siehe auch

[#Import Attribute](../preprocessor/hash-import-attributes-cpp.md)\
[#Import-Direktive](../preprocessor/hash-import-directive-cpp.md)
