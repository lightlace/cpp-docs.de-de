---
title: __svm_vmrun
ms.date: 11/04/2016
f1_keywords:
- __svm_vmrun
helpviewer_keywords:
- __svm_vmrun intrinsic
- VMRUN instruction
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
ms.openlocfilehash: 40e53b2ebd54fc109b47f3067e5f89ce50b327de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390203"
---
# <a name="svmvmrun"></a>__svm_vmrun

**Microsoft-spezifisch**

Startet die Ausführung der VM-Gast-Code, der die den angegebenen virtuellen Computer-Kontrollblock (VMCB) entspricht.

## <a name="syntax"></a>Syntax

```
void __svm_vmrun(
   size_t VmcbPhysicalAddress
);
```

#### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*VmcbPhysicalAddress*|[in] Die physische Adresse der VMCB.|

## <a name="remarks"></a>Hinweise

Die `__svm_vmrun` Funktion verwendet eine minimale Menge an Informationen in den VMCB, um zu beginnen, den VM-Gast-Code ausführen. Verwenden der [__svm_vmsave](../intrinsics/svm-vmsave.md) oder [__svm_vmload](../intrinsics/svm-vmload.md) ausgeführt werden, wenn Sie weitere Informationen zu einem komplexen Unterbrechung zu verarbeiten oder wechseln Sie zu einem anderen Gast benötigen.

Die `__svm_vmrun` -Funktion entspricht der `VMRUN` -Computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen zu suchen, für das Dokument, "AMD64 Architecture Programmers manuelle Volume 2: "System Programming," Dokumentnummer 24593, Version 3.11 oder höher, auf die [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) Standort.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__svm_vmrun`|x86, x64|

**Headerdatei** \<intrin.h >

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[__svm_vmsave](../intrinsics/svm-vmsave.md)<br/>
[__svm_vmload](../intrinsics/svm-vmload.md)