---
title: inject_statement
ms.date: 10/18/2018
f1_keywords:
- inject_statement
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
ms.openlocfilehash: 237ca796028aad7aff55442eb2806fe400330a29
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034286"
---
# <a name="injectstatement"></a>inject_statement

**C++-spezifisch**

Fügt das Argument als Quelltext in den Header der Typbibliothek ein.

## <a name="syntax"></a>Syntax

```
inject_statement("source_text")
```

### <a name="parameters"></a>Parameter

*source_text*<br/>
In die Headerdatei der Typbibliothek einzufügender Quelltext.

## <a name="remarks"></a>Hinweise

Der Text wird am Anfang der Namespacedeklaration platziert, die den Typbibliotheksinhalt in der Headerdatei umschließt.

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)