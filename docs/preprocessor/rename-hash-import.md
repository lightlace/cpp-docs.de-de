---
title: Umbenennen (#import) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- Rename
dev_langs:
- C++
helpviewer_keywords:
- rename attribute
ms.assetid: 5c5c6153-1087-4b7b-87fb-fc59b90b9975
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b8525a321f56ab5e9bfe2f8e8cee7be9cd26788
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808185"
---
# <a name="rename-import"></a>Umbenennen (\#importieren)

**C++-spezifisch**

Umgeht Probleme mit Namenskonflikten.

## <a name="syntax"></a>Syntax

```
rename("OldName","NewName")
```

### <a name="parameters"></a>Parameter

*Alter Name*<br/>
Alter Name in der Typbibliothek.

*Neuer Name*<br/>
Name, der anstelle des alten Namens verwendet werden soll.

## <a name="remarks"></a>Hinweise

Wenn dieses Attribut angegeben wird, wird der Compiler ersetzt alle Vorkommen von *OldName* in eine Typbibliothek mit den vom Benutzer bereitgestellten *NewName* in den resultierenden Headerdateien.

Dieses Attribut kann verwendet werden, wenn ein Name in der Typbibliothek einer Makrodefinition in den Systemheaderdateien entspricht. Wenn diese Situation nicht aufgelöst, unterschiedliche Syntaxfehler generiert werden, z. B. [Compilerfehler C2059](../error-messages/compiler-errors-1/compiler-error-c2059.md) und [Compilerfehler C2061](../error-messages/compiler-errors-1/compiler-error-c2061.md).

> [!NOTE]
> Die Ersetzung erfolgt für einen in der Typbibliothek verwendeten, nicht für einen in der resultierenden Headerdatei verwendeten Namen.

Angenommen, eine Eigenschaft mit dem Namen `MyParent` ist in einer Typbibliothek vorhanden und das Makro `GetMyParent` wird in einer Headerdatei definiert und vor `#import` verwendet. Da `GetMyParent` ist der Standardname einer Wrapperfunktion für die Fehlerbehandlung `get` -Eigenschaft, es wird ein Namenskonflikt auftreten. Um das Problem zu umgehen, verwenden Sie das folgende Attribut in der `#import`-Anweisung:

```cpp
rename("MyParent","MyParentX")
```

das den Namen `MyParent` in der Typbibliothek umbenennt. Bei dem Versuch, den Wrappernamen `GetMyParent` umzubenennen, tritt ein Fehler auf:

```cpp
rename("GetMyParent","GetMyParentX")
```

Dies ist darauf zurückzuführen, dass der Name `GetMyParent` nur in der resultierenden Typbibliotheksheaderdatei auftritt.

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)