---
title: __halt
ms.date: 09/02/2019
f1_keywords:
- __halt
- __halt_cpp
helpviewer_keywords:
- __halt intrinsic
- HLT instruction
ms.assetid: a074f44a-101c-45a5-8a5e-cfd223c34002
ms.openlocfilehash: 66f5e05e7673523966ef35ac743fc585930b511c
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222150"
---
# <a name="__halt"></a>__halt

**Microsoft-spezifisch**

Stoppt den Mikroprozessor, bis ein aktivierter Interrupt, ein nicht Maskier barer Interrupt (NMI) oder eine zurück Setzung auftritt.

## <a name="syntax"></a>Syntax

```C
void __halt( void );
```

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__halt`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Die `__halt` -Funktion entspricht der `HLT` -Computer Anweisung und ist nur im Kernel Modus verfügbar. Weitere Informationen finden Sie im Dokument "Intel Architecture Software Developer es Manual, Volume 2: Anweisungs Satz Verweis "auf der Website der [Intel Corporation](https://software.intel.com/articles/intel-sdm) .

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
