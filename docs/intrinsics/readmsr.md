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
ms.openlocfilehash: 2c866213c452f3b8791bf0fe031a43bb024e91fb
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59027627"
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