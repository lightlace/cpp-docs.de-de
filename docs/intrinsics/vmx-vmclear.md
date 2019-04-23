---
title: __vmx_vmclear
ms.date: 11/04/2016
f1_keywords:
- __vmx_vmclear
helpviewer_keywords:
- VMCLEAR instruction
- __vmx_vmclear intrinsic
ms.assetid: e3eb98e4-50fc-4c93-9bac-340fd1f0a466
ms.openlocfilehash: 17e3e5c91a58894b25fc6b2a72f7d0056fa88119
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59036536"
---
# <a name="vmxvmclear"></a>__vmx_vmclear

**Microsoft-spezifisch**

Initialisiert die Steuerelement-Struktur des angegebenen virtuellen Computer (VMCS) und legt seinen Start-Zustand auf `Clear`.

## <a name="syntax"></a>Syntax

```
unsigned char __vmx_vmclear(
   unsigned __int64 *VmcsPhysicalAddress
);
```

#### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*VmcsPhysicalAddress*|[in] Ein Zeiger auf einen 64-Bit-Speicherbereich, der die physische Adresse der VMCS löschen enthält.|

## <a name="return-value"></a>Rückgabewert

|Wert|Bedeutung|
|-----------|-------------|
|0|Der Vorgang wurde erfolgreich ausgeführt.|
|1|Bei dem Vorgang ist ein Fehler mit erweitertem Status aufgetreten, der im `VM-instruction error field` der aktuellen VMCS verfügbar ist.|
|2|Bei dem Vorgang ist ein Fehler ohne verfügbaren Status aufgetreten.|

## <a name="remarks"></a>Hinweise

Eine Anwendung kann einen VM-enter-Vorgang ausführen, indem Sie entweder die [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) oder [__vmx_vmresume](../intrinsics/vmx-vmresume.md) Funktion. Die [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) Funktion kann verwendet werden, nur mit einer VMCS, deren Startstatus `Clear`, und die [__vmx_vmresume](../intrinsics/vmx-vmresume.md) Funktion kann verwendet werden, nur mit einer VMCS, deren Startstatus `Launched`. Verwenden Sie daher die [__vmx_vmclear](../intrinsics/vmx-vmclear.md) -Funktion zum Festlegen des einer VMCS auf Startstatus `Clear`. Verwenden der [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) -Funktion für den ersten VM-enter-Vorgang und die [__vmx_vmresume](../intrinsics/vmx-vmresume.md) -Funktion für nachfolgende Vorgänge auf VM-enter.

Die `__vmx_vmclear` -Funktion entspricht der `VMCLEAR` -Computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Dokumentieren Sie weitere Informationen suchen Sie nach dem Dokument "Intel Virtualization Technical Specification for the IA-32 Intel Architecture," Dokumentnummer C97063-002 auf der [Intel Corporation](https://software.intel.com/articles/intel-sdm) Standort.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__vmx_vmclear`|x64|

**Headerdatei** \<intrin.h >

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)<br/>
[__vmx_vmresume](../intrinsics/vmx-vmresume.md)