---
title: raw_dispinterfaces
ms.date: 11/04/2016
f1_keywords:
- raw_dispinterfaces
helpviewer_keywords:
- raw_dispinterfaces attribute
ms.assetid: f762864d-29bf-445b-825a-ba7b29a95409
ms.openlocfilehash: ef8ed3992c77df0f1d551e923ddc90c2d1bb9b0b
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59027922"
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