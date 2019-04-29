---
title: __svm_invlpga
ms.date: 11/04/2016
f1_keywords:
- __svm_invlpga
helpviewer_keywords:
- __svm_invlpga intrinsic
- INVLPGA instruction
ms.assetid: aa6578ce-8278-464b-8815-a0fc45330915
ms.openlocfilehash: 5e470fc12ad47aa156c513b293543fa356398d5e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390268"
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
|*Va*|[in] Die virtuelle Adresse der Seite für ungültig erklärt werden soll.|
|*ASID*|[in] Die Adresse Speicherplatz Bezeichner (ASID) der Seite für ungültig erklärt.|

## <a name="remarks"></a>Hinweise

Die `__svm_invlpga` -Funktion entspricht der `INVLPGA` -Computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen zu suchen, für das Dokument, "AMD64 Architecture Programmers manuelle Volume 2: "System Programming," Dokumentnummer 24593, Version 3.11, auf die [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) Standort.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__svm_invlpga`|x86, x64|

**Headerdatei** \<intrin.h >

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)