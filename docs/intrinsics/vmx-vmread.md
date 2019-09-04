---
title: __vmx_vmread
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmread
helpviewer_keywords:
- VMREAD instruction
- __vmx_vmread intrinsic
ms.assetid: 08bdd7a0-6435-4ea6-b9a0-f592d870e5aa
ms.openlocfilehash: 409835ac29d6f2e839de62291cc5b142166a465c
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219431"
---
# <a name="__vmx_vmread"></a>__vmx_vmread

**Microsoft-spezifisch**

Liest ein angegebenes Feld aus der aktuellen VM-Steuerungsstruktur (Virtual Machine Control Structure, VMCS) und platziert es am angegebenen Speicherort.

## <a name="syntax"></a>Syntax

```C
unsigned char __vmx_vmread(
   size_t Field,
   size_t *FieldValue
);
```

### <a name="parameters"></a>Parameter

*Flächen*\
in Das zu lesende VMCS-Feld.

*Feldwert*\
in Ein Zeiger auf den Speicherort, an dem der aus dem vom- `Field` Parameter angegebenen VMCS-Feld gelesene Wert gespeichert wird.

## <a name="return-value"></a>Rückgabewert

|Wert|Bedeutung|
|-----------|-------------|
|0|Der Vorgang wurde erfolgreich ausgeführt.|
|1|Bei dem Vorgang ist ein Fehler mit erweitertem Status aufgetreten, der im `VM-instruction error field` der aktuellen VMCS verfügbar ist.|
|2|Bei dem Vorgang ist ein Fehler ohne verfügbaren Status aufgetreten.|

## <a name="remarks"></a>Hinweise

Die `__vmx_vmread` -Funktion entspricht der `VMREAD` -Computeranweisung. Der Wert des `Field` -Parameters ist ein codierter Feldindex, der in der Intel-Dokumentation beschrieben wird. Weitere Informationen finden Sie in Anhang C der "Intel Virtualization Technical Specification for the IA-32 Intel Architecture" auf der Website der [Intel Corporation](https://software.intel.com/articles/intel-sdm) .

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__vmx_vmread`|x64|

**Header Datei** \<intrin. h->

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmwrite](../intrinsics/vmx-vmwrite.md)
