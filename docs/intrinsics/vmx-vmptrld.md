---
title: __vmx_vmptrld
ms.date: 11/04/2016
f1_keywords:
- __vmx_vmptrld
helpviewer_keywords:
- __vmx_vmptrld intrinsic
- VMPTRLD instruction
ms.assetid: 95c9ec5b-1a81-41ba-983e-327bd6a65fcb
ms.openlocfilehash: e3d552720d454a4f22af368616b3953452c6db0e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59040422"
---
# <a name="vmxvmptrld"></a>__vmx_vmptrld

**Microsoft-spezifisch**

Lädt den Zeiger auf die aktuellen VM-Steuerelement-Struktur (VMCS) aus der angegebenen Adresse an.

## <a name="syntax"></a>Syntax

```
int __vmx_vmptrld(
   unsigned __int64 *VmcsPhysicalAddress
);
```

### <a name="parameters"></a>Parameter

*VmcsPhysicalAddress*<br/>
[in] Die Adresse, wo der Zeiger VMCS gespeichert werden.

## <a name="return-value"></a>Rückgabewert

0<br/>
Der Vorgang wurde erfolgreich ausgeführt.

1<br/>
Bei dem Vorgang ist ein Fehler mit erweitertem Status aufgetreten, der im `VM-instruction error field` der aktuellen VMCS verfügbar ist.

2<br/>
Bei dem Vorgang ist ein Fehler ohne verfügbaren Status aufgetreten.

## <a name="remarks"></a>Hinweise

Der Zeiger VMCS ist eine physische 64-Bit-Adresse.

Die `__vmx_vmptrld` -Funktion entspricht der `VMPTRLD` -Computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Dokumentieren Sie weitere Informationen suchen Sie nach dem Dokument "Intel Virtualization Technical Specification for the IA-32 Intel Architecture," Dokumentnummer C97063-002 auf der [Intel Corporation](https://software.intel.com/articles/intel-sdm) Standort.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__vmx_vmptrld`|x64|

**Headerdatei** \<intrin.h >

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmptrst](../intrinsics/vmx-vmptrst.md)