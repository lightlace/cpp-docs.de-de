---
title: ".MODEL"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - ".MODEL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".MODEL directive"
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# .MODEL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Initialisiert das Programm Speichermodell.  
  
## Syntax  
  
```  
.MODEL memorymodel [[, langtype]] [[, stackoption]]  
```  
  
#### Parameter  
 `memorymodel`  
 Erforderlicher Parameter, der die Größe von Code und Daten\-Zeigern bestimmt.  
  
 `langtype`  
 Optionaler Parameter, der die Konventionen aufrufen und Benennungskonventionen für Prozeduren und öffentliche Symbole festlegt.  
  
 `stackoption`  
 Optionaler Parameter.  
  
 `stackoption`is not used if `memorymodel` is `FLAT`.  
  
 Angabe `NEARSTACK` gruppiert Stapelsegments liegt in einer einzigen physikalischen Komponente \(`DGROUP`\) zusammen mit den Daten.  Das Segment\-Stapelregister \(`SS`\) wird angenommen, dass die gleiche Adresse wie die Segmentregister Daten halten \(`DS`\).  `FARSTACK`gruppiert nicht den Stapel mit `DGROUP`; So `SS` ist nicht gleich `DS`.  
  
## Hinweise  
 .`MODEL`wird [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
 Die folgende Tabelle listet die möglichen Werte für jeden Parameter, wenn 16\-Bit\- und 32\-Bit\-Plattformen:  
  
|Parameter|32\-Bit\-Werte|16\-Bit\-Werte \(Unterstützung für ältere 16\-Bit\-Entwicklung\)|  
|---------------|--------------------|----------------------------------------------------------------------|  
|`memorymodel`|`FLAT`|`TINY`, `SMALL`, `COMPACT`, `MEDIUM`, `LARGE`, `HUGE`, `FLAT`|  
|`langtype`|`C`, `STDCALL`|`C`, `BASIC`, `FORTRAN`, `PASCAL`, `SYSCALL`, `STDCALL`|  
|`stackoption`|Nicht in Verwendung|`NEARSTACK`, `FARSTACK`|  
  
## Code  
 Im Zusammenhang mit MASM\-Beispiele downloaden Compilerbeispiele aus [Visual C\+\+\-Beispiele und Dokumentation für das Jahr 2010 Visual Studio](http://go.microsoft.com/fwlink/?LinkID=178749).  
  
 Das folgende Beispiel veranschaulicht die Verwendung der `.MODEL` Richtlinie.  
  
## Beispiel  
  
```  
; file simple.asm  
; For x86 (32-bit), assemble with debug information:   
;   ml -c -Zi simple.asm  
; For x64 (64-bit), assemble with debug information:   
;   ml64 -c -DX64 -Zi simple.asm  
;  
; In this sample, the 'X64' define excludes source not used   
;  when targeting the x64 architecture  
  
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
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)   
 [Visual C\+\+\-Beispiele und Dokumentation für das Jahr 2010 Visual Studio](http://go.microsoft.com/fwlink/?LinkID=178749)