---
title: __vmx_vmwrite
ms.date: 11/04/2016
f1_keywords:
- __vmx_vmwrite
helpviewer_keywords:
- __vmx_vmwrite intrinsic
- VMWRITE instruction
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
ms.openlocfilehash: c5c6e0edcb3136986cfd8e05f3d5217b3d021fa7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529245"
---
# <a name="vmxvmwrite"></a>__vmx_vmwrite

**Microsoft-spezifisch**

Schreibt den angegebenen Wert in das angegebene Feld in der aktuellen VM-Steuerelement-Struktur (VMCS).

## <a name="syntax"></a>Syntax

```
unsigned char __vmx_vmwrite( 
   size_t Field,
   size_t FieldValue
);
```

#### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Feld*|[in] Das VMCS-Feld geschrieben werden soll.|
|*FieldValue*|[in] Der Wert in das Feld "VMCS" geschrieben.|

## <a name="return-value"></a>Rückgabewert

0, die der Vorgang erfolgreich war.

1 Vorgangsfehler mit erweitertem Status zur Verfügung, in der `VM-instruction error field` von der aktuellen VMCS.

2 Fehler ohne verfügbaren Status.

## <a name="remarks"></a>Hinweise

Die `__vmx_vmwrite` -Funktion entspricht der `VMWRITE` -Computeranweisung. Der Wert des der `Field` -Parameter ist eine codierte Feldindex, die in der Intel-Dokumentation beschrieben ist. Dokumentieren Sie weitere Informationen suchen Sie nach dem Dokument "Intel Virtualization Technical Specification for the IA-32 Intel Architecture," Dokumentnummer C97063-002 auf der [Intel Corporation](https://software.intel.com/articles/intel-sdm) Standorts aus, und klicken Sie dann finden Sie in Anhang C, Dokument.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__vmx_vmwrite`|x64|

**Headerdatei** \<intrin.h >

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmread](../intrinsics/vmx-vmread.md)