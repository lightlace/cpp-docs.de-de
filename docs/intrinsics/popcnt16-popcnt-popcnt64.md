---
title: __popcnt16, __popcnt, __popcnt64 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __popcnt64
- __popcnt
- __popcnt16
dev_langs:
- C++
helpviewer_keywords:
- popcnt instruction
- __popcnt16
- __popcnt64
- __popcnt
ms.assetid: e525b236-adc8-42df-9b9b-8b7d8c245d3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 34063223addb433a94c877ad56cf410f189e6681
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45724735"
---
# <a name="popcnt16-popcnt-popcnt64"></a>__popcnt16, __popcnt, __popcnt64

**Microsoft-spezifisch**  
  
 Zählt die Anzahl von einem Bits (Population Count) in einen 16-, 32- oder 64-Byte-Ganzzahl ohne Vorzeichen.  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned short __popcnt16(  
   unsigned short value  
);  
unsigned int __popcnt(  
   unsigned int value  
);  
unsigned __int64 __popcnt64(  
   unsigned __int64 value  
);  
```  
  
#### <a name="parameters"></a>Parameter  
*Wert*<br/>
[in] Die 16, 32- oder 64-Bit-Ganzzahl ohne Vorzeichen für die die Anzahl der Auffüllen soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bits in der `value` Parameter.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__popcnt16`|Erweiterte Bitmanipulation|  
|`__popcnt`|Erweiterte Bitmanipulation|  
|`__popcnt64`|Erweiterte Bitmanipulation in 64-Bit-Modus.|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Jede von diesen systeminternen Funktionen generiert der `popcnt` Anweisung.  Die Größe des Werts, der die `popcnt` Anweisung zurückgibt, ist die Größe des Arguments identisch.  In 32-Bit-Modus sind keine 64-Bit-Allzweckregister, daher keine 64-Bit- `popcnt`.  
  
 Um zu bestimmen, Hardware-Unterstützung für die `popcnt` -Anweisung, rufen die `__cpuid` systeminternen Funktionen mit `InfoType=0x00000001` und überprüfen Sie wenig 23 `CPUInfo[2] (ECX)`. Dieses Bit ist 1, wenn die Anweisung unterstützt wird, und andernfalls 0. Wenn Sie Code, verwendet dieser systeminternen Funktion auf Hardware ausgeführt, die nicht unterstützt. die `popcnt` -Anweisung, die die Ergebnisse sind unvorhersehbar.  
  
## <a name="example"></a>Beispiel  
  
```  
#include <iostream>   
#include <intrin.h>   
using namespace std;   
  
int main()   
{  
  unsigned short us[3] = {0, 0xFF, 0xFFFF};  
  unsigned short usr;  
  unsigned int   ui[4] = {0, 0xFF, 0xFFFF, 0xFFFFFFFF};  
  unsigned int   uir;  
  
  for (int i=0; i<3; i++) {  
    usr = __popcnt16(us[i]);  
    cout << "__popcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;  
  }  
  
  for (int i=0; i<4; i++) {  
    uir = __popcnt(ui[i]);  
    cout << "__popcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;  
  }  
}  
  
```  
  
```Output  
__popcnt16(0x0) = 0  
__popcnt16(0xff) = 8  
__popcnt16(0xffff) = 16  
__popcnt(0x0) = 0  
__popcnt(0xff) = 8  
__popcnt(0xffff) = 16  
__popcnt(0xffffffff) = 32  
```  
  
**Ende Microsoft-spezifisch**  

Copyright 2007 erweiterten Micro-Geräte, Inc. Alle Rechte vorbehalten. Reproduziert werden, mit der Berechtigung, die von erweiterten Micro-Geräte, Inc.  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
