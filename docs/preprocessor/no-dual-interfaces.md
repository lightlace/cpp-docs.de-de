---
title: No_dual_interfaces | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_dual_interfaces
dev_langs:
- C++
helpviewer_keywords:
- no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6dcf63933a54983fcf98e35acce533670dc74ed4
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50070958"
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