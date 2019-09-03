---
title: __svm_vmrun
ms.date: 09/02/2019
f1_keywords:
- __svm_vmrun
helpviewer_keywords:
- __svm_vmrun intrinsic
- VMRUN instruction
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
ms.openlocfilehash: f23df894cc8ad1c270c4c0acbc97cab727e47d93
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219825"
---
# <a name="__svm_vmrun"></a>__svm_vmrun

**Microsoft-spezifisch**

Startet die Ausführung des Gast Codes der virtuellen Maschine, der dem angegebenen Virtual Machine Control Block (VMCB) entspricht.

## <a name="syntax"></a>Syntax

```C
void __svm_vmrun(
   size_t VmcbPhysicalAddress
);
```

### <a name="parameters"></a>Parameter

*Vmcbphysicaladdress*\
in Die physische Adresse des VMCB.

## <a name="remarks"></a>Hinweise

Die `__svm_vmrun` Funktion verwendet eine minimale Menge an Informationen in VMCB, um mit der Ausführung des Gast Codes der virtuellen Maschine zu beginnen. Verwenden Sie die [__svm_vmsave](../intrinsics/svm-vmsave.md) -oder [__svm_vmload](../intrinsics/svm-vmload.md) -Funktion, wenn Sie weitere Informationen benötigen, um einen komplexen Interrupt zu verarbeiten oder zu einem anderen Gast zu wechseln.

Die `__svm_vmrun` -Funktion entspricht der `VMRUN` -Computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen finden Sie im Dokument "amd64 Architecture Programmer es Manual Volume 2: System Programmierung, "Dokument Nummer 24593, Revision 3,11 oder höher, am Standort der [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) .

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__svm_vmrun`|x86, x64|

**Header Datei** \<intrin. h->

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[__svm_vmsave](../intrinsics/svm-vmsave.md)\
[__svm_vmload](../intrinsics/svm-vmload.md)
