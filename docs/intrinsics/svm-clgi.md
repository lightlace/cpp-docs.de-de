---
title: __svm_clgi
ms.date: 09/02/2019
f1_keywords:
- __svm_clgi
helpviewer_keywords:
- CLGI instruction
- __svm_clgi intrinsic
ms.assetid: 6640f5ab-9472-46f9-a042-e15c4f1ff858
ms.openlocfilehash: 740c76e5dcc8f94b9257272624a6ad3c1f9726c1
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219973"
---
# <a name="__svm_clgi"></a>__svm_clgi

**Microsoft-spezifisch**

Löscht das globale Interrupt-Flag.

## <a name="syntax"></a>Syntax

```C
void __svm_clgi( void );
```

## <a name="remarks"></a>Hinweise

Die `__svm_clgi` -Funktion entspricht der `CLGI` -Computeranweisung. Das Flag für das globale Interrupt bestimmt, ob der Mikroprozessor aufgrund von Ereignissen wie einer e/a-Vervollständigung, einer Hardware Temperatur Warnung oder einer Debug-Ausnahme Interrupts ignoriert, Postpones oder behandelt.

Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen finden Sie, wenn Sie nach "amd64 Architecture Programmer es Manual Volume 2: System Programmierung: auf der [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) -Website.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__svm_clgi`|x86, x64|

**Header Datei** \<intrin. h->

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[__svm_stgi](../intrinsics/svm-stgi.md)
