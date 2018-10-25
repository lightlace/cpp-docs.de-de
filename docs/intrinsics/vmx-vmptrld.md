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
ms.openlocfilehash: 16a61578b7512c1d9ce9d7ca217b29a3ea670657
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50068488"
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