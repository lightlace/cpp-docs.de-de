---
title: __vmx_on
ms.date: 11/04/2016
f1_keywords:
- __vmx_on
helpviewer_keywords:
- VMXON instruction
- __vmx_on intrinsic
ms.assetid: 16804991-6a75-4adf-8ec2-bc95acfa4801
ms.openlocfilehash: de903eeeb29e3c194a36ccb4cb038ba89b8ea82f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59028103"
---
# <a name="vmxon"></a>__vmx_on

**Microsoft-spezifisch**

VM-Erweiterungen (VMX) Vorgang im Prozessor wird aktiviert.

## <a name="syntax"></a>Syntax

```
unsigned char __vmx_on(
   unsigned __int64 *VmsSupportPhysicalAddress
);
```

#### <a name="parameters"></a>Parameter

*VmsSupportPhysicalAddress*<br/>
[in] Ein Zeiger auf eine physische 64-Bit-Adresse, die auf einer VM-Steuerelement-Struktur (VMCS) verweist.

## <a name="return-value"></a>Rückgabewert

|Wert|Bedeutung|
|-----------|-------------|
|0|Der Vorgang wurde erfolgreich ausgeführt.|
|1|Bei dem Vorgang ist ein Fehler mit erweitertem Status aufgetreten, der im `VM-instruction error field` der aktuellen VMCS verfügbar ist.|
|2|Bei dem Vorgang ist ein Fehler ohne verfügbaren Status aufgetreten.|

## <a name="remarks"></a>Hinweise

Die `__vmx_on` Funktion entspricht der `VMXON` computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Dokumentieren Sie weitere Informationen suchen Sie nach dem Dokument "Intel Virtualization Technical Specification for the IA-32 Intel Architecture," Dokumentnummer C97063-002 auf der [Intel Corporation](https://software.intel.com/articles/intel-sdm) Standort.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__vmx_on`|x64|

**Headerdatei** \<intrin.h >

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)