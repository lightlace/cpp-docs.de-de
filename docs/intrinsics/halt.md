---
title: __halt
ms.date: 11/04/2016
f1_keywords:
- __halt
- __halt_cpp
helpviewer_keywords:
- __halt intrinsic
- HLT instruction
ms.assetid: a074f44a-101c-45a5-8a5e-cfd223c34002
ms.openlocfilehash: d99a87b1f3fd70d1fffb724629e9acded025732a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50617177"
---
# <a name="halt"></a>__halt

**Microsoft-spezifisch**

Hält den Mikroprozessor, bis eine aktivierte Unterbrechung, einen nicht maskierbaren Interrupt (NMI) oder eine Zurücksetzung erfolgt.

## <a name="syntax"></a>Syntax

```
void __halt( void );
```

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__halt`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Die `__halt` -Funktion ist gleichbedeutend mit der `HLT` computeranweisung und steht nur im Kernelmodus ausgeführt. Weitere Informationen zu suchen, nach dem Dokument "Intel Architecture-Softwareentwickler manuell, Volume 2: Instruction Set Reference," auf die [Intel Corporation](https://software.intel.com/articles/intel-sdm) Standort.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)