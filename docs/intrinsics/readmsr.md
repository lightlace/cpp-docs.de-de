---
title: __readmsr
ms.date: 11/04/2016
f1_keywords:
- __readmsr
helpviewer_keywords:
- Read Model Specific Register
- rdmsr instruction
- __readmsr intrinsic
ms.assetid: 7ab1f8e8-72cb-4ce4-817d-3e728a3c9716
ms.openlocfilehash: 891ca43af4a81b63de39d367ea418e43811f78d0
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326406"
---
# <a name="readmsr"></a>__readmsr

**Microsoft-spezifisch**

Generiert die `rdmsr` -Anweisung, die das modellspezifische Register gemäß liest `register` und den Wert zurückgibt.

## <a name="syntax"></a>Syntax

```
__int64 __readmsr(
   int register
);
```

#### <a name="parameters"></a>Parameter

*register*<br/>
[in] Das Modell bestimmte Register lesen.

## <a name="return-value"></a>Rückgabewert

Der Wert im angegebenen Register.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__readmsr`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Diese Funktion ist nur im Kernelmodus verfügbar, und die Routine ist nur als systeminterne Funktion verfügbar.

Weitere Informationen finden Sie in der AMD-Dokumentation.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)