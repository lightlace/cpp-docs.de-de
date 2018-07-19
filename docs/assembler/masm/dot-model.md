---
title: . MODELL | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .MODEL
dev_langs:
- C++
helpviewer_keywords:
- .MODEL directive
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2814b1b6cc4483807f77989ff4fbb70929400d6e
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057746"
---
# <a name="model"></a>.MODEL
Initialisiert das Programm Speicher-Modell.  
  
## <a name="syntax"></a>Syntax  
  
```  
.MODEL memorymodel [[, langtype]] [[, stackoption]]  
```  
  
#### <a name="parameters"></a>Parameter  
 `memorymodel`  
 Erforderlicher Parameter, der die Größe der Zeiger für Code und Daten bestimmt.  
  
 `langtype`  
 Optionaler Parameter, der die Konventionen aufrufenden und Benennungskonventionen für Prozeduren und die öffentlichen Symbole festlegt.  
  
 `stackoption`  
 Optionaler Parameter.  
  
 `stackoption` wird nicht verwendet werden, wenn `memorymodel` ist `FLAT`.  
  
 Angeben von `NEARSTACK` gruppiert die Aufruflistensegment in einem einzigen physischen Segment (`DGROUP`) zusammen mit Daten. Das Stapelregister-Segment (`SS`) wird davon ausgegangen, dass dieselbe Adresse wie der Segment-Datenregister halten (`DS`). `FARSTACK` den Stapel mit werden nicht gruppiert `DGROUP`daher `SS` stimmt nicht mit `DS`.  
  
## <a name="remarks"></a>Hinweise  
 .`MODEL` wird nicht verwendet werden, [MASM für X64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
 In der folgenden Tabelle sind die möglichen Werte für jeden Parameter aufgeführt, wenn 16-Bit- und 32-Bit-Zielplattformen:  
  
|Parameter|32-Bit-Werte|16-Bit-Werte (Unterstützung für die Entwicklung von früheren 16-Bit)|  
|---------------|--------------------|----------------------------------------------------------------|  
|`memorymodel`|`FLAT`|`TINY`, `SMALL`, `COMPACT`, `MEDIUM`, `LARGE`, `HUGE`, `FLAT`|  
|`langtype`|`C`, `STDCALL`|`C`, `BASIC`, `FORTRAN`, `PASCAL`, `SYSCALL`, `STDCALL`|  
|`stackoption`|Nicht verwendet|`NEARSTACK`, `FARSTACK`|  
  
## <a name="code"></a>Code  
 MASM-bezogene Beispiele Herunterladen der Compilerbeispiele von [Visual C++-Beispiele und Dokumentationen für Visual Studio 2010](http://go.microsoft.com/fwlink/p/?linkid=178749).  
  
 Das folgende Beispiel veranschaulicht die Verwendung von der `.MODEL` Richtlinie.  
  
## <a name="example"></a>Beispiel  
  
```  
; file simple.asm  
; For x86 (32-bit), assemble with debug information:   
;   ml -c -Zi simple.asm  
; For x64 (64-bit), assemble with debug information:   
;   ml64 -c -DX64 -Zi simple.asm  
;  
; In this sample, the 'X64' define excludes source not used   
;  when targeting the x64 architecture  
  
ifndef X64  
.686p  
.XMM  
.model flat, C  
endif  
  
.data  
; user data  
  
.code  
; user code  
  
fxn PROC public  
  xor eax, eax ; zero function return value  
  ret  
fxn ENDP  
  
end  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Direktiven – Referenz](../../assembler/masm/directives-reference.md)   
 [Visual C++-Beispiele und Dokumentationen für Visual Studio 2010](http://go.microsoft.com/fwlink/p/?linkid=178749)