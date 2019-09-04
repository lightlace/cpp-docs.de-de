---
title: __vmx_vmlaunch
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmlaunch
helpviewer_keywords:
- VMLAUNCH instruction
- __vmx_vmlaunch intrinsic
ms.assetid: 708f7c38-b7c1-4ee7-bfc4-0daeb9cc9360
ms.openlocfilehash: 8d78e5181fdd43e10431e12d0cf540c8c9c2e719
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219546"
---
# <a name="__vmx_vmlaunch"></a>__vmx_vmlaunch

**Microsoft-spezifisch**

Platziert die aufrufenden Anwendung mithilfe der aktuellen Virtual-Machine-Steuerungsstruktur (Virtual Machine Control Structure, VMCS) im VMX-Betriebsstatus nicht Stamm (VM Enter).

## <a name="syntax"></a>Syntax

```C
unsigned char __vmx_vmlaunch(void);
```

## <a name="return-value"></a>Rückgabewert

|Wert|Bedeutung|
|-----------|-------------|
|0|Der Vorgang wurde erfolgreich ausgeführt.|
|1|Bei dem Vorgang ist ein Fehler mit erweitertem Status aufgetreten, der im `VM-instruction error field` der aktuellen VMCS verfügbar ist.|
|2|Bei dem Vorgang ist ein Fehler ohne verfügbaren Status aufgetreten.|

## <a name="remarks"></a>Hinweise

Eine Anwendung kann einen "VM-Enter"-Vorgang mithilfe der [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) -Funktion oder der [__vmx_vmresume](../intrinsics/vmx-vmresume.md) -Funktion ausführen. Die [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) -Funktion kann nur mit einer VMCS verwendet werden, deren Start `Clear`Status ist, und die [__vmx_vmresume](../intrinsics/vmx-vmresume.md) -Funktion kann nur mit einer VMCS verwendet werden, `Launched`deren Startstatus lautet. Verwenden Sie daher die [__vmx_vmclear](../intrinsics/vmx-vmclear.md) -Funktion, um den Startstatus einer VMCS auf `Clear`festzulegen, und verwenden Sie dann die [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) -Funktion für Ihren ersten VM-Enter-Vorgang und die [__vmx_vmresume](../intrinsics/vmx-vmresume.md) -Funktion für nachfolgende VM-Enter. Operations.

Die `__vmx_vmlaunch` -Funktion entspricht der `VMLAUNCH` -Computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen finden Sie im Dokument "Intel Virtualization Technical Specification for the IA-32 Intel Architecture" Dokument Nummer C97063-002 auf der Website der [Intel Corporation](https://software.intel.com/articles/intel-sdm) .

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__vmx_vmlaunch`|x64|

**Header Datei** \<intrin. h->

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmresume](../intrinsics/vmx-vmresume.md)\
[__vmx_vmclear](../intrinsics/vmx-vmclear.md)
