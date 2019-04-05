---
title: no_namespace
ms.date: 11/04/2016
f1_keywords:
- no_namespace
helpviewer_keywords:
- no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
ms.openlocfilehash: f6bd60de02bf0166d5cf0b0cd1bc1de56ceda5bf
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59028716"
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