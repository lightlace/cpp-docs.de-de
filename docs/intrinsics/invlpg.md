---
title: __invlpg
ms.date: 09/02/2019
f1_keywords:
- __invlpg
- __invlpg_cpp
helpviewer_keywords:
- invlpg instruction
- __invlpg intrinsic
ms.assetid: 3fb3633f-d9b7-4ec0-9e7f-a7f2fa8ed794
ms.openlocfilehash: ba8bd81498f805992336b0dc4163fe18fa157a2c
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221896"
---
# <a name="__invlpg"></a>__invlpg

**Microsoft-spezifisch**

Generiert die x86 `invlpg` -Anweisung, die den Translation Lookaside Buffer (TLB) für die Seite, die dem Speicher zugeordnet ist, auf den von *Address*verwiesen wird, ungültig macht.

## <a name="syntax"></a>Syntax

```C
void __invlpg(
   void* Address
);
```

### <a name="parameters"></a>Parameter

*Adresse*\
in Eine 64-Bit-Adresse.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__invlpg`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

`__invlpg` Die systeminterne Funktion gibt eine privilegierte Anweisung aus und ist nur im Kernel Modus mit der Berechtigungsstufe "0" verfügbar.

Diese Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
