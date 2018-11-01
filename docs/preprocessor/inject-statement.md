---
title: Inject_statement | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- inject_statement
dev_langs:
- C++
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 27b35c10e9e1953dc45dee1caf61d2e58c38d02d
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808642"
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