---
title: __svm_clgi | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __svm_clgi
dev_langs:
- C++
helpviewer_keywords:
- CLGI instruction
- __svm_clgi intrinsic
ms.assetid: 6640f5ab-9472-46f9-a042-e15c4f1ff858
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 378dd025b4db769645ca53a01504c195c1265ac6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410597"
---
# <a name="svmclgi"></a>__svm_clgi

**Microsoft-spezifisch**

Löscht das globale Interrupt-Flag an.

## <a name="syntax"></a>Syntax

```
void __svm_clgi( void );
```

## <a name="remarks"></a>Hinweise

Die `__svm_clgi` -Funktion ist gleichbedeutend mit der `CLGI` computeranweisung. Das globale Interrupt-Flag bestimmt, ob der Mikroprozessor ignoriert, verschiebt oder Unterbrechungen, z. B. durch einen e/a-Abschluss, eine temperaturwarnung Hardware oder eine debugausnahme behandelt.

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