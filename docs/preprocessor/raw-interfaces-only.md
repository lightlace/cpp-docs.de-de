---
title: Raw_interfaces_only | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_interfaces_only
dev_langs:
- C++
helpviewer_keywords:
- raw_interfaces_only attribute
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 789c9179b2ba48f5c3796f709931728bc756aaaa
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50075033"
---
# <a name="rawinterfacesonly"></a>raw_interfaces_only
**C++-spezifisch**

Unterdrückt die Generierung von Fehlerbehandlungs Wrapperfunktionen und [Eigenschaft](../cpp/property-cpp.md) Deklarationen, die diese Wrapperfunktionen verwenden.

## <a name="syntax"></a>Syntax

```
raw_interfaces_only
```

## <a name="remarks"></a>Hinweise

Die **Raw_interfaces_only** -Attribut bewirkt auch, dass das Standardpräfix verwendet wird, benennen Sie die Funktionen ohne Eigenschaft entfernt werden soll. Normalerweise ist das Präfix ist **Raw_**. Wenn dieses Attribut festgelegt wird, stammen die Funktionsnamen direkt aus der Typbibliothek.

Dieses Attribut ermöglicht, dass Sie nur die Inhalte auf niedriger Ebene aus der Typbibliothek verfügbar machen.

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)