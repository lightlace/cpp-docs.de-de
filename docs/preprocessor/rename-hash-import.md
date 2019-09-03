---
title: Import Attribut umbenennen
ms.date: 08/29/2019
f1_keywords:
- Rename
helpviewer_keywords:
- rename attribute
ms.assetid: 5c5c6153-1087-4b7b-87fb-fc59b90b9975
ms.openlocfilehash: ef1f64e0c268f850899efe499f7b1ad3991dd570
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216662"
---
# <a name="rename-import-attribute"></a>Import Attribut umbenennen

**C++Zugeschnitten**

Umgeht Probleme mit Namenskonflikten.

## <a name="syntax"></a>Syntax

> **#Import** *Typbibliothek* **Rename (** "*OldName*" **,** "*NewName*" **)**

### <a name="parameters"></a>Parameter

*OldName*\
Alter Name in der Typbibliothek.

*NewName*\
Name, der anstelle des alten Namens verwendet werden soll.

## <a name="remarks"></a>Hinweise

Wenn das **Rename** -Attribut angegeben wird, ersetzt der Compiler alle Vorkommen von *OldName* in der *Type-Library* durch den vom Benutzer bereitgestellten *NewName* in den resultierenden Header Dateien.

Das **Rename** -Attribut kann verwendet werden, wenn ein Name in der Typbibliothek mit einer Makro Definition in den System Header Dateien übereinstimmt. Wenn diese Situation nicht behoben ist, gibt der Compiler möglicherweise verschiedene Syntax Fehler aus, z. b. [Compilerfehler C2059](../error-messages/compiler-errors-1/compiler-error-c2059.md) und [Compilerfehler C2061](../error-messages/compiler-errors-1/compiler-error-c2061.md).

> [!NOTE]
> Die Ersetzung erfolgt für einen in der Typbibliothek verwendeten, nicht für einen in der resultierenden Headerdatei verwendeten Namen.

Angenommen, eine Eigenschaft mit dem Namen `MyParent` ist in einer Typbibliothek vorhanden und das Makro `GetMyParent` wird in einer Headerdatei definiert und vor `#import` verwendet. Da `GetMyParent` der Standardname einer Wrapper Funktion für die Fehler Behandlungs `get` Eigenschaft ist, tritt ein namens Konflikt auf. Um das Problem zu umgehen, verwenden Sie das folgende Attribut in der `#import`-Anweisung:

```cpp
#import MyTypeLib.tlb rename("MyParent","MyParentX")
```

das den Namen `MyParent` in der Typbibliothek umbenennt. Bei dem Versuch, den Wrappernamen `GetMyParent` umzubenennen, tritt ein Fehler auf:

```cpp
#import MyTypeLib.tlb rename("GetMyParent","GetMyParentX")
```

Der Grund hierfür ist, `GetMyParent` dass der Name nur in der resultierenden Header Datei der Typbibliothek auftritt.

**End C++ -Specific**

## <a name="see-also"></a>Siehe auch

[#Import Attribute](../preprocessor/hash-import-attributes-cpp.md)\
[#Import-Direktive](../preprocessor/hash-import-directive-cpp.md)
