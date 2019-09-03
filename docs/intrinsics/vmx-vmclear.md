---
title: __vmx_vmclear
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmclear
helpviewer_keywords:
- VMCLEAR instruction
- __vmx_vmclear intrinsic
ms.assetid: e3eb98e4-50fc-4c93-9bac-340fd1f0a466
ms.openlocfilehash: 3b5807402cf0a9d8a9ef1ded1d112d22a801633e
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219544"
---
# <a name="__vmx_vmclear"></a>__vmx_vmclear

**Microsoft-spezifisch**

Initialisiert die angegebene VM-Steuerungsstruktur (Virtual Machine Control Structure, VMCS) und `Clear`legt deren Startstatus auf fest.

## <a name="syntax"></a>Syntax

```C
unsigned char __vmx_vmclear(
   unsigned __int64 *VmcsPhysicalAddress
);
```

### <a name="parameters"></a>Parameter

*Vmcsphysicaladdress*\
in Ein Zeiger auf einen Speicherort mit 64-Bit-Speicher, der die physische Adresse der zu löschenden VMCS enthält.

## <a name="return-value"></a>Rückgabewert

|Wert|Bedeutung|
|-----------|-------------|
|0|Der Vorgang wurde erfolgreich ausgeführt.|
|1|Bei dem Vorgang ist ein Fehler mit erweitertem Status aufgetreten, der im `VM-instruction error field` der aktuellen VMCS verfügbar ist.|
|2|Bei dem Vorgang ist ein Fehler ohne verfügbaren Status aufgetreten.|

## <a name="remarks"></a>Hinweise

Eine Anwendung kann einen "VM-Enter"-Vorgang mithilfe der [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) -Funktion oder der [__vmx_vmresume](../intrinsics/vmx-vmresume.md) -Funktion ausführen. Die [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) -Funktion kann nur mit einer VMCS verwendet werden, deren Start `Clear`Status ist, und die [__vmx_vmresume](../intrinsics/vmx-vmresume.md) -Funktion kann nur mit einer VMCS verwendet werden, `Launched`deren Startstatus lautet. Verwenden Sie daher die [__vmx_vmclear](../intrinsics/vmx-vmclear.md) -Funktion, um den Startstatus einer VMCS auf `Clear`festzulegen. Verwenden Sie die [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) -Funktion für den ersten "VM-Enter"-Vorgang und die [__vmx_vmresume](../intrinsics/vmx-vmresume.md) -Funktion für nachfolgende VM-Enter-Vorgänge.

Die `__vmx_vmclear` -Funktion entspricht der `VMCLEAR` -Computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen finden Sie im Dokument "Intel Virtualization Technical Specification for the IA-32 Intel Architecture" Dokument Nummer C97063-002 auf der Website der [Intel Corporation](https://software.intel.com/articles/intel-sdm) .

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__vmx_vmclear`|x64|

**Header Datei** \<intrin. h->

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)\
[__vmx_vmresume](../intrinsics/vmx-vmresume.md)
