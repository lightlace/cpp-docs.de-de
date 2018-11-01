---
title: __vmx_vmlaunch
ms.date: 11/04/2016
f1_keywords:
- __vmx_vmlaunch
helpviewer_keywords:
- VMLAUNCH instruction
- __vmx_vmlaunch intrinsic
ms.assetid: 708f7c38-b7c1-4ee7-bfc4-0daeb9cc9360
ms.openlocfilehash: 70c26da61d1ba9a8e5dc52d6fb0318fad918f525
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512973"
---
# <a name="vmxvmlaunch"></a>__vmx_vmlaunch

**Microsoft-spezifisch**

Platziert die aufrufende Anwendung in der VMX-Vorgang ohne Stamm-Zustand (Geben Sie virtuelle Computer) mithilfe der aktuellen VM-Steuerelement-Struktur (VMCS).

## <a name="syntax"></a>Syntax

```
unsigned char __vmx_vmlaunch(
   void);
```

## <a name="return-value"></a>Rückgabewert

|Wert|Bedeutung|
|-----------|-------------|
|0|Der Vorgang wurde erfolgreich ausgeführt.|
|1|Bei dem Vorgang ist ein Fehler mit erweitertem Status aufgetreten, der im `VM-instruction error field` der aktuellen VMCS verfügbar ist.|
|2|Bei dem Vorgang ist ein Fehler ohne verfügbaren Status aufgetreten.|

## <a name="remarks"></a>Hinweise

Eine Anwendung kann einen VM-enter-Vorgang ausführen, indem Sie entweder die [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) oder [__vmx_vmresume](../intrinsics/vmx-vmresume.md) Funktion. Die [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) Funktion kann verwendet werden, nur mit einer VMCS, deren Startstatus `Clear`, und die [__vmx_vmresume](../intrinsics/vmx-vmresume.md) Funktion kann verwendet werden, nur mit einer VMCS, deren Startstatus `Launched`. Verwenden Sie daher die [__vmx_vmclear](../intrinsics/vmx-vmclear.md) -Funktion zum Festlegen des einer VMCS auf Startstatus `Clear`, und verwenden Sie dann die [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) -Funktion für den ersten VM-enter-Vorgang und der [__vmx_vmresume](../intrinsics/vmx-vmresume.md) -Funktion für nachfolgende Vorgänge auf VM-enter.

Die `__vmx_vmlaunch` -Funktion entspricht der `VMLAUNCH` -Computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Dokumentieren Sie weitere Informationen suchen Sie nach dem Dokument "Intel Virtualization Technical Specification for the IA-32 Intel Architecture," Dokumentnummer C97063-002 auf der [Intel Corporation](https://software.intel.com/articles/intel-sdm) Standort.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__vmx_vmlaunch`|x64|

**Headerdatei** \<intrin.h >

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmresume](../intrinsics/vmx-vmresume.md)<br/>
[__vmx_vmclear](../intrinsics/vmx-vmclear.md)