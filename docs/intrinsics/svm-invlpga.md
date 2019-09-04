---
title: __svm_invlpga
ms.date: 09/02/2019
f1_keywords:
- __svm_invlpga
helpviewer_keywords:
- __svm_invlpga intrinsic
- INVLPGA instruction
ms.assetid: aa6578ce-8278-464b-8815-a0fc45330915
ms.openlocfilehash: e0f8ef02efdb64f70bb65f6f017449fcc03beca1
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219884"
---
# <a name="__svm_invlpga"></a>__svm_invlpga

**Microsoft-spezifisch**

Erklärt den Adress Zuordnungseintrag in der Übersetzung der Übersetzung der Übersetzung des Computers für ungültig. Parameter geben die virtuelle Adresse und den Adressraum Bezeichner der Seite an, die für ungültig erklärt werden soll.

## <a name="syntax"></a>Syntax

```C
void __svm_invlpga(void *Vaddr, int as_id);
```

### <a name="parameters"></a>Parameter

*Vaddr*\
in Die virtuelle Adresse der Seite, die für ungültig erklärt werden soll.

*as_id*\
in Der für ungültig zu erklärenden Wert der Adressraum Kennung (ASID) der Seite.

## <a name="remarks"></a>Hinweise

Die `__svm_invlpga` -Funktion entspricht der `INVLPGA` -Computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen finden Sie im Dokument "amd64 Architecture Programmer es Manual Volume 2: System Programmierung "Dokument Nummer 24593, Revision 3,11, am Standort der [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) .

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__svm_invlpga`|x86, x64|

**Header Datei** \<intrin. h->

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
