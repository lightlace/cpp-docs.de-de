---
title: Raw_dispinterfaces | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_dispinterfaces
dev_langs:
- C++
helpviewer_keywords:
- raw_dispinterfaces attribute
ms.assetid: f762864d-29bf-445b-825a-ba7b29a95409
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b89c1f549168a762b5ae095c4eacf5ddb1b4d053
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50062348"
---
# <a name="rawdispinterfaces"></a>raw_dispinterfaces
**C++-spezifisch**

Weist den Compiler an, Wrapperfunktionen auf niedriger Ebene für Disp-Schnittstellenmethoden und Eigenschaften, die aufgerufen werden generieren `IDispatch::Invoke` und den HRESULT-Fehlercode zurückgegeben.

## <a name="syntax"></a>Syntax

```
raw_dispinterfaces
```

## <a name="remarks"></a>Hinweise

Wenn dieses Attribut nicht angegeben wird, werden nur Wrapper auf hoher Ebene generiert, die im Falle eines Fehlers C++-Ausnahmen auslösen.

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)