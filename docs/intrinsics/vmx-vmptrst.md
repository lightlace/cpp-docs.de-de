---
title: __vmx_vmptrst
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmptrst
helpviewer_keywords:
- __vmx_vmptrst intrinsic
- VMPTRST instruction
ms.assetid: 8dc66e47-03a0-41b0-8e25-c1485f42817a
ms.openlocfilehash: e559746be9e2a3fe5e81afa4d290265394db3e36
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219489"
---
# <a name="__vmx_vmptrst"></a>__vmx_vmptrst

**Microsoft-spezifisch**

Speichert den Zeiger auf die aktuelle Virtual Machine Control-Struktur (VMCS) an der angegebenen Adresse.

## <a name="syntax"></a>Syntax

```C
void __vmx_vmptrst(
   unsigned __int64 *VmcsPhysicalAddress
);
```

### <a name="parameters"></a>Parameter

*Vmcsphysicaladdress*\
in Die Adresse, in der der aktuelle VMCS-Zeiger gespeichert wird.

## <a name="remarks"></a>Hinweise

Der VMCS-Zeiger ist eine physische 64-Bit-Adresse.

Die `__vmx_vmptrst` -Funktion entspricht der `VMPTRST` -Computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen finden Sie im Dokument "Intel Virtualization Technical Specification for the IA-32 Intel Architecture" Dokument Nummer C97063-002 auf der Website der [Intel Corporation](https://software.intel.com/articles/intel-sdm) .

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__vmx_vmptrst`|x86, x64|

**Header Datei** \<intrin. h->

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmptrld](../intrinsics/vmx-vmptrld.md)
