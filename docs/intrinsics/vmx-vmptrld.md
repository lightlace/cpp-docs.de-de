---
title: __vmx_vmptrld | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmptrld
dev_langs:
- C++
helpviewer_keywords:
- __vmx_vmptrld intrinsic
- VMPTRLD instruction
ms.assetid: 95c9ec5b-1a81-41ba-983e-327bd6a65fcb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a7126dc3b6a0ece4a5b7627859d0b80abf962d88
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429102"
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

#### <a name="parameters"></a>Parameter

[in] *`VmcsPhysicalAddress` die Adresse, in der VMCS Zeiger gespeichert ist.

## <a name="return-value"></a>Rückgabewert

0, die der Vorgang erfolgreich war.

1 Vorgangsfehler mit erweitertem Status zur Verfügung, in der `VM-instruction error field` von der aktuellen VMCS.

2 Fehler ohne verfügbaren Status.

## <a name="remarks"></a>Hinweise

Der Zeiger VMCS ist eine physische 64-Bit-Adresse.

Die `__vmx_vmptrld` -Funktion ist gleichbedeutend mit der `VMPTRLD` computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Dokumentieren Sie weitere Informationen suchen Sie nach dem Dokument "Intel Virtualization Technical Specification for the IA-32 Intel Architecture," Dokumentnummer C97063-002 auf der [Intel Corporation](https://software.intel.com/en-us/articles/intel-sdm) Standort.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__vmx_vmptrld`|x64|

**Headerdatei** \<intrin.h >

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmptrst](../intrinsics/vmx-vmptrst.md)