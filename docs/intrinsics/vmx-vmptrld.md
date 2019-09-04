---
title: __vmx_vmptrld
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmptrld
helpviewer_keywords:
- __vmx_vmptrld intrinsic
- VMPTRLD instruction
ms.assetid: 95c9ec5b-1a81-41ba-983e-327bd6a65fcb
ms.openlocfilehash: 79b5a8b34b652ae1f011e89c793a7157c9e435ee
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219495"
---
# <a name="__vmx_vmptrld"></a>__vmx_vmptrld

**Microsoft-spezifisch**

Lädt den Zeiger auf die aktuelle Virtual Machine Control-Struktur (VMCS) aus der angegebenen Adresse.

## <a name="syntax"></a>Syntax

```C
int __vmx_vmptrld(
   unsigned __int64 *VmcsPhysicalAddress
);
```

### <a name="parameters"></a>Parameter

*Vmcsphysicaladdress*\
in Die Adresse, in der der VMCS-Zeiger gespeichert wird.

## <a name="return-value"></a>Rückgabewert

1,0
Der Vorgang wurde erfolgreich ausgeführt.

1
Bei dem Vorgang ist ein Fehler mit erweitertem Status aufgetreten, der im `VM-instruction error field` der aktuellen VMCS verfügbar ist.

2,2
Bei dem Vorgang ist ein Fehler ohne verfügbaren Status aufgetreten.

## <a name="remarks"></a>Hinweise

Der VMCS-Zeiger ist eine physische 64-Bit-Adresse.

Die `__vmx_vmptrld` -Funktion entspricht der `VMPTRLD` -Computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen finden Sie im Dokument "Intel Virtualization Technical Specification for the IA-32 Intel Architecture" Dokument Nummer C97063-002 auf der Website der [Intel Corporation](https://software.intel.com/articles/intel-sdm) .

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__vmx_vmptrld`|x64|

**Header Datei** \<intrin. h->

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmptrst](../intrinsics/vmx-vmptrst.md)
