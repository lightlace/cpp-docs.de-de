---
title: __vmx_off
ms.date: 09/02/2019
f1_keywords:
- __vmx_off
helpviewer_keywords:
- VMXOFF instruction
- __vmx_off intrinsic
ms.assetid: 78a32d46-9291-406c-b982-a550855aff18
ms.openlocfilehash: 226b5111c2f4f6771ac75d165c80c3e8ae2336af
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219593"
---
# <a name="__vmx_off"></a>__vmx_off

**Microsoft-spezifisch**

Deaktiviert den VMX-Vorgang (Virtual Machine Extensions) im Prozessor.

## <a name="syntax"></a>Syntax

```C
void __vmx_off();
```

## <a name="remarks"></a>Hinweise

Die `__vmx_off` -Funktion entspricht der `VMXOFF` -Computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen finden Sie im Dokument "Intel Virtualization Technical Specification for the IA-32 Intel Architecture" Dokument Nummer C97063-002 auf der Website der [Intel Corporation](https://software.intel.com/articles/intel-sdm) .

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__vmx_off`|x86, x64|

**Header Datei** \<intrin. h->

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
