---
title: __svm_vmload
ms.date: 09/02/2019
f1_keywords:
- __svm_vmload
helpviewer_keywords:
- __svm_vmload intrinsic
- VMLOAD instruction
ms.assetid: b46a5592-db76-4ffc-8694-2f3494e28bed
ms.openlocfilehash: da6ca9786b9c7e5041b9a8ca908d567b16176436
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219810"
---
# <a name="__svm_vmload"></a>__svm_vmload

**Microsoft-spezifisch**

Lädt eine Teilmenge des Prozessor Zustands aus dem angegebenen Virtual Machine Control Block (VMCB).

## <a name="syntax"></a>Syntax

```C
void __svm_vmload(
   size_t VmcbPhysicalAddress
);
```

### <a name="parameters"></a>Parameter

*Vmcbphysicaladdress*\
in Die physische Adresse des VMCB.

## <a name="remarks"></a>Hinweise

Die `__svm_vmload` -Funktion entspricht der `VMLOAD` -Computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen finden Sie im Dokument "amd64 Architecture Programmer es Manual Volume 2: System Programmierung "Dokument Nummer 24593, Revision 3,11, am Standort der [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) .

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__svm_vmload`|x86, x64|

**Header Datei** \<intrin. h->

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[__svm_vmrun](../intrinsics/svm-vmrun.md)\
[__svm_vmsave](../intrinsics/svm-vmsave.md)
