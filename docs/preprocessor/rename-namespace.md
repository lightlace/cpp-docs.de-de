---
title: rename_namespace
ms.date: 10/18/2018
f1_keywords:
- rename_namespace
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
ms.openlocfilehash: 7b3917a7114ca44d092f10a7831bb35bc64e9387
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59039873"
---
# <a name="renamenamespace"></a>rename_namespace

**C++-spezifisch**

Benennt den Namespace, der die Inhalte der Typbibliothek enthält, um.

## <a name="syntax"></a>Syntax

```
rename_namespace("NewName")
```

### <a name="parameters"></a>Parameter

*NewName*<br/>
Der neue Name des neuen Namespace.

## <a name="remarks"></a>Hinweise

Es dauert ein einzelnes Argument, *NewName*, die den neuen Namen für den Namespace angibt.

Verwenden Sie zum Entfernen des Namespaces der [No_namespace](../preprocessor/no-namespace.md) Attribut.

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)