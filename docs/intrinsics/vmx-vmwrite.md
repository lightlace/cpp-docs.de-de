---
title: __vmx_vmwrite
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmwrite
helpviewer_keywords:
- __vmx_vmwrite intrinsic
- VMWRITE instruction
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
ms.openlocfilehash: cdc5590858f160db24bf75ef11c8f20b204a3152
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219393"
---
# <a name="__vmx_vmwrite"></a>__vmx_vmwrite

**Microsoft-spezifisch**

Schreibt den angegebenen Wert in das angegebene Feld in der aktuellen VM-Steuerungsstruktur (Virtual Machine Control Structure, VMCS).

## <a name="syntax"></a>Syntax

```C
unsigned char __vmx_vmwrite(
   size_t Field,
   size_t FieldValue
);
```

### <a name="parameters"></a>Parameter

*Flächen*\
in Das zu schreibende VMCS-Feld.

*Feldwert*\
in Der Wert, der in das Feld VMCS geschrieben werden soll.

## <a name="return-value"></a>Rückgabewert

1,0
Der Vorgang wurde erfolgreich ausgeführt.

1
Bei dem Vorgang ist ein Fehler mit erweitertem Status aufgetreten, der im `VM-instruction error field` der aktuellen VMCS verfügbar ist.

2,2
Bei dem Vorgang ist ein Fehler ohne verfügbaren Status aufgetreten.

## <a name="remarks"></a>Hinweise

Die `__vmx_vmwrite` -Funktion entspricht der `VMWRITE` -Computeranweisung. Der Wert des `Field` -Parameters ist ein codierter Feldindex, der in der Intel-Dokumentation beschrieben wird. Weitere Informationen finden Sie in Anhang C der "Intel Virtualization Technical Specification for the IA-32 Intel Architecture" auf der Website der [Intel Corporation](https://software.intel.com/articles/intel-sdm) .

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__vmx_vmwrite`|x64|

**Header Datei** \<intrin. h->

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmread](../intrinsics/vmx-vmread.md)
