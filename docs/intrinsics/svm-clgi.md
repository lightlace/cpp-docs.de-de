---
title: __svm_clgi
ms.date: 11/04/2016
f1_keywords:
- __svm_clgi
helpviewer_keywords:
- CLGI instruction
- __svm_clgi intrinsic
ms.assetid: 6640f5ab-9472-46f9-a042-e15c4f1ff858
ms.openlocfilehash: 9f3484cc5cbffea1315d546ced317dfdfceee9e6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618869"
---
# <a name="svmclgi"></a>__svm_clgi

**Microsoft-spezifisch**

Löscht das globale Interrupt-Flag an.

## <a name="syntax"></a>Syntax

```
void __svm_clgi( void );
```

## <a name="remarks"></a>Hinweise

Die `__svm_clgi` -Funktion entspricht der `CLGI` -Computeranweisung. Das globale Interrupt-Flag bestimmt, ob der Mikroprozessor ignoriert, verschiebt oder Unterbrechungen, z. B. durch einen e/a-Abschluss, eine temperaturwarnung Hardware oder eine debugausnahme behandelt.

Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen zu suchen, für das Dokument, "AMD64 Architecture Programmers manuelle Volume 2: System-Programmierung" Dokumentnummer 24593, Version 3.11, auf die [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) Standort.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__svm_clgi`|x86, x64|

**Headerdatei** \<intrin.h >

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[__svm_stgi](../intrinsics/svm-stgi.md)