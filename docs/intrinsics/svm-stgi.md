---
title: __svm_stgi
ms.date: 09/02/2019
f1_keywords:
- __svm_stgi
helpviewer_keywords:
- __svm_stgi intrinsic
- STGI instruction
ms.assetid: 96488da4-5587-4e99-8674-627a9e51be84
ms.openlocfilehash: 6bd731951b440d3d2597d54c9a52d9f8640a5c5f
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219832"
---
# <a name="__svm_stgi"></a>__svm_stgi

**Microsoft-spezifisch**

Legt das Flag für das globale Interrupt fest.

## <a name="syntax"></a>Syntax

```C
void __svm_stgi(void);
```

## <a name="remarks"></a>Hinweise

Die `__svm_stgi` -Funktion entspricht der `STGI` -Computeranweisung. Das Flag für das globale Interrupt bestimmt, ob der Mikroprozessor aufgrund von Ereignissen wie einer e/a-Vervollständigung, einer Hardware Temperatur Warnung oder einer Debug-Ausnahme Interrupts ignoriert, Postpones oder behandelt.

Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen finden Sie, wenn Sie nach "amd64 Architecture Programmer es Manual Volume 2: System Programmierung: auf der [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) -Website.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__svm_stgi`|x86, x64|

**Header Datei** \<intrin. h->

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[__svm_clgi](../intrinsics/svm-clgi.md)
