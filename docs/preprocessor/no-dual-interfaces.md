---
title: no_dual_interfaces
ms.date: 11/04/2016
f1_keywords:
- no_dual_interfaces
helpviewer_keywords:
- no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
ms.openlocfilehash: d76fe3ce6bea4c3895da9d8b40d69852f912824e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466728"
---
# <a name="nodualinterfaces"></a>no_dual_interfaces
**C++-spezifisch**

Ändert die Art, mit der der Compiler Wrapperfunktionen für Methoden der dualen Schnittstelle generiert.

## <a name="syntax"></a>Syntax

```
no_dual_interfaces
```

## <a name="remarks"></a>Hinweise

Normalerweise ruft der Wrapper die Methode über die virtuelle Funktionstabelle für die Schnittstelle auf. Mit **No_dual_interfaces**, ruft der Wrapper stattdessen `IDispatch::Invoke` zum Aufrufen der Methode.

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)