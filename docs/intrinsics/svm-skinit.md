---
title: __svm_skinit
ms.date: 09/02/2019
f1_keywords:
- __svm_skinit
helpviewer_keywords:
- SKINIT instruction
- __svm_skinit intrinsic
ms.assetid: 787ec781-4cf2-40a2-aa20-5192334b131a
ms.openlocfilehash: 6657921d647a23bf027a5800702527951f7f6831
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219867"
---
# <a name="__svm_skinit"></a>__svm_skinit

**Microsoft-spezifisch**

Initiiert das Laden von überprüfbar sicheren Software, z. b. einem Monitor für virtuelle Maschinen.

## <a name="syntax"></a>Syntax

```C
void __svm_skinit(
   int block_address
);
```

### <a name="parameters"></a>Parameter

*block_address*\
Die physische 32-Bit-Adresse eines Secure Loader Block-Blocks (SLB) mit 64K Byte.

## <a name="remarks"></a>Hinweise

Die `__svm_skinit` -Funktion entspricht der `SKINIT` -Computeranweisung. Diese Funktion ist Teil eines Sicherheitssystems, in dem der Prozessor und ein Trusted Platform Module (TPM) verwendet werden, um vertrauenswürdige Software zu überprüfen und zu laden, die als *Sicherheits Kernel* (SK) bezeichnet wird. Ein virtueller Computermonitor ist ein Beispiel für einen sicherheitskerneltyp. Das Sicherheitssystem überprüft Programmkomponenten, die während des Initialisierungs Vorgangs geladen wurden. Sie schützt Komponenten vor Manipulationen durch Interrupts, Gerätezugriff oder ein anderes Programm, wenn der Computer ein Multiprozessor ist.

Der *block_address* -Parameter gibt die physische Adresse eines Speicherblocks von 64 KB an, der als *Secure Loader Block* (SLB) bezeichnet wird. Der SLB enthält ein Programm, das als *sicheres Lade*Programm bezeichnet wird. Dadurch wird die Betriebsumgebung für den Computer festgelegt, und anschließend wird der Sicherheitstokendienst geladen.

Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen finden Sie, wenn Sie nach "amd64 Architecture Programmer es Manual Volume 2: System Programmierung: auf der [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) -Website.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__svm_skinit`|x86, x64|

**Header Datei** \<intrin. h->

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
