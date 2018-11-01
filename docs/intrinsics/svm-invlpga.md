---
title: __svm_invlpga | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __svm_invlpga
dev_langs:
- C++
helpviewer_keywords:
- __svm_invlpga intrinsic
- INVLPGA instruction
ms.assetid: aa6578ce-8278-464b-8815-a0fc45330915
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3fa5655911366b0adf21618ec7be7eeccdca9c5a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401906"
---
# <a name="svminvlpga"></a>__svm_invlpga

**Microsoft-spezifisch**

Erklärt den Adresseintrag für die Zuordnung im Puffer suchen-Aside-Übersetzung, des Computers an. Parameter geben die virtuelle Adresse und die Adresse Raum-ID der Seite für ungültig erklärt.

## <a name="syntax"></a>Syntax

```
void __svm_invlpga(void *Va, int ASID);
```

#### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*VA*|[in] Die virtuelle Adresse der Seite für ungültig erklärt werden soll.|
|*ASID*|[in] Die Adresse Speicherplatz Bezeichner (ASID) der Seite für ungültig erklärt.|

## <a name="remarks"></a>Hinweise

Die `__svm_invlpga` -Funktion ist gleichbedeutend mit der `INVLPGA` computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen zu suchen, für das Dokument, "AMD64 Architecture Programmers manuelle Volume 2: System-Programmierung" Dokumentnummer 24593, Version 3.11, auf die [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) Standort.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__svm_invlpga`|x86, x64|

**Headerdatei** \<intrin.h >

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)