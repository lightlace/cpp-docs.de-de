---
title: __svm_vmsave
ms.date: 11/04/2016
f1_keywords:
- __svm_vmsave
helpviewer_keywords:
- VMSAVE instruction
- __svm_vmsave intrinsic
ms.assetid: 617a60bd-8514-4ba1-8066-bcf4dd481030
ms.openlocfilehash: d683a13f636db9683b4a7c8d075ad6c3c88c2aed
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023411"
---
# <a name="svmvmsave"></a>__svm_vmsave

**Microsoft-spezifisch**

Eine Teilmenge der Prozessorzustand wird in der angegebenen virtuellen Computer-Kontrollblock (VMCB) gespeichert.

## <a name="syntax"></a>Syntax

```
void __svm_vmsave(
   size_t VmcbPhysicalAddress
);
```

#### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*VmcbPhysicalAddress*|[in] Die physische Adresse der VMCB.|

## <a name="remarks"></a>Hinweise

Die `__svm_vmsave` -Funktion entspricht der `VMSAVE` -Computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen zu suchen, für das Dokument, "AMD64 Architecture Programmers manuelle Volume 2: "System Programming," Dokumentnummer 24593, Version 3.11 oder höher, auf die [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) Standort.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__svm_vmsave`|x86, x64|

**Headerdatei** \<intrin.h >

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[__svm_vmrun](../intrinsics/svm-vmrun.md)<br/>
[__svm_vmload](../intrinsics/svm-vmload.md)