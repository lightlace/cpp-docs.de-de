---
title: include ()-Import Attribut
ms.date: 08/29/2019
f1_keywords:
- include()
helpviewer_keywords:
- include() attribute
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
ms.openlocfilehash: 39ab63525b2b83781cbcaf86a61742c5fb767b72
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218881"
---
# <a name="include-import-attribute"></a>include ()-Import Attribut

**C++Zugeschnitten**

Deaktiviert den automatische Ausschluss.

## <a name="syntax"></a>Syntax

> **#Import** *Typbibliothek* **include ("** _Name1_ **"** [ __, "__ *name2* __"__ ...] __)__

### <a name="parameters"></a>Parameter

*Name1*\
Das erste Element, dessen Aufnahme erzwungen wird.

*Name2*\
Das zweite Element, dessen Aufnahme erzwungen wird (falls erforderlich).

## <a name="remarks"></a>Hinweise

Typbibliotheken können Definitionen der Elemente enthalten, die in Systemheadern oder anderen Typbibliotheken definiert sind. `#import` versucht, mehrfache Definitionsfehler dadurch zu vermeiden, dass solche Elemente automatisch ausgeschlossen werden. Wenn einige Elemente nicht automatisch ausgeschlossen werden sollen, wird möglicherweise die Compilerwarnung [(Stufe 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md)angezeigt. Sie können dieses Attribut verwenden, um den automatischen Ausschluss zu deaktivieren. Dieses Attribut kann eine beliebige Anzahl von Argumenten annehmen, eine für jeden Namen eines Typbibliotheks Elements, das eingeschlossen werden soll.

**End C++ -Specific**

## <a name="see-also"></a>Siehe auch

[#Import Attribute](../preprocessor/hash-import-attributes-cpp.md)\
[#Import-Direktive](../preprocessor/hash-import-directive-cpp.md)
