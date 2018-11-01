---
title: no_namespace
ms.date: 11/04/2016
f1_keywords:
- no_namespace
helpviewer_keywords:
- no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
ms.openlocfilehash: b17bf5fb5f44d5453de29febe001f9e8737102b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540438"
---
# <a name="nonamespace"></a>no_namespace
**C++-spezifisch**

Gibt an, dass der Name des Namespaces nicht vom Compiler generiert wird.

## <a name="syntax"></a>Syntax

```
no_namespace
```

## <a name="remarks"></a>Hinweise

Der Inhalt der Typbibliothek in der `#import`-Headerdatei wird normalerweise in einem Namespace definiert. Der Namespacename wird angegeben, der `library` -Anweisung der ursprünglichen IDL-Datei. Wenn die **No_namespace** -Attribut angegeben ist, wird dieser Namespace wird nicht vom Compiler generiert.

Wenn Sie einen anderen Namespacenamen verwenden möchten, verwenden Sie die [Rename_namespace](../preprocessor/rename-namespace.md) Attribut.

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)