---
title: __svm_stgi
ms.date: 11/04/2016
f1_keywords:
- __svm_stgi
helpviewer_keywords:
- __svm_stgi intrinsic
- STGI instruction
ms.assetid: 96488da4-5587-4e99-8674-627a9e51be84
ms.openlocfilehash: ea138f17a24af21afa937991f77bd1e2a689c3f7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390216"
---
# <a name="svmstgi"></a>__svm_stgi

**Microsoft-spezifisch**

Legt das globale Interrupt-Flag fest.

## <a name="syntax"></a>Syntax

```
void __svm_stgi(void);
```

## <a name="remarks"></a>Hinweise

Die `__svm_stgi` -Funktion entspricht der `STGI` -Computeranweisung. Das globale Interrupt-Flag bestimmt, ob der Mikroprozessor ignoriert, verschiebt oder Unterbrechungen, z. B. durch einen e/a-Abschluss, eine temperaturwarnung Hardware oder eine debugausnahme behandelt.

Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen zu suchen, für das Dokument, "AMD64 Architecture Programmers manuelle Volume 2: "System Programming," Dokumentnummer 24593, Version 3.11, auf die [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) Standort.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__svm_stgi`|x86, x64|

**Headerdatei** \<intrin.h >

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[__svm_clgi](../intrinsics/svm-clgi.md)