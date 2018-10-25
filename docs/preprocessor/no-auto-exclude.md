---
title: No_auto_exclude | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_auto_exclude
dev_langs:
- C++
helpviewer_keywords:
- no_auto_exclude attribute
ms.assetid: 3241ef9c-758a-4e86-bdc5-37da6072430f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0673a7216bc00fb13cb0c99e0f9b74accabe33b0
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50074966"
---
# <a name="noautoexclude"></a>no_auto_exclude
**C++-spezifisch**

Deaktiviert den automatische Ausschluss.

## <a name="syntax"></a>Syntax

```
no_auto_exclude
```

## <a name="remarks"></a>Hinweise

Typbibliotheken können Definitionen der Elemente enthalten, die in Systemheadern oder anderen Typbibliotheken definiert sind. `#import` versucht, mehrfache Definitionsfehler dadurch zu vermeiden, dass solche Elemente automatisch ausgeschlossen werden. Wenn dies abgeschlossen ist, [Compilerwarnung (Stufe 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md) für die einzelnen Elemente ausgeschlossen werden ausgegeben. Sie können diesen automatischen Ausschluss deaktivieren, indem Sie dieses Attribut verwenden.

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)