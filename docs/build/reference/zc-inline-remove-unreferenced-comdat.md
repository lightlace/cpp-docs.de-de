---
title: "/Zc:inline (unreferenzierte COMDAT entfernen)"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "/Zc:inline"
  - "VC.Project.VCCLCompilerTool.RemoveUnreferencedCodeData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc (Compileroptionen) [C++]"
  - "/Zc:inline"
  - "Zc (Compileroptionen) [C++]"
  - "-Zc (Compileroptionen) [C++]"
ms.assetid: a4c94224-1d73-4bea-a9d5-4fa73dc924df
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# /Zc:inline (unreferenzierte COMDAT entfernen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Entfernt unreferenzierte Funktionen oder Daten, die COMDATs sind oder nur eine interne Bindung haben.  Wenn **\/Zc:inline** angegeben wird, erfordert der Compiler, dass Übersetzungseinheiten, die Inlinedaten oder Inlinefunktionen verwenden, auch die Definitionen für die Daten oder Funktionen enthalten müssen.  
  
## Syntax  
  
```  
/Zc:inline[-]  
```  
  
## Hinweise  
 Wenn **\/Zc:inline** angegeben wird, gibt der Compiler keine Symbolinformationen für unreferenzierte COMDAT\-Funktionen oder \-Daten oder für Funktionen oder Daten, die nur eine interne Bindung haben, zurück.  Diese Option ist standardmäßig deaktiviert \(**\/Zc:inline\-**\).  Diese Optimierung vereinfacht einen Teil der Arbeit, die vom Linker in Releasebuilds oder wenn die Linkeroption [\/OPT:REF](../../build/reference/opt-optimizations.md) angegeben ist, durchgeführt wird.  Wenn der Compiler diese Optimierung durchführt, kann er die Größe der .obj\-Datei deutlich verringern und Linkergeschwindigkeiten verbessern.  Diese Compileroption ist nicht aktiviert, wenn Optimierungen deaktiviert sind \([\/Od](../../build/reference/od-disable-debug.md)\) oder [\/GL \(Optimierung des ganzen Programms\)](../../build/reference/gl-whole-program-optimization.md) angegeben wird.  
  
 Wenn **\/Zc:inline** angegeben wird, erzwingt der Compiler die C\+\+11\-Anforderung, dass alle Funktionen, die als `inline` deklariert sind, über eine Definition in derselben Übersetzungseinheit verfügen müssen, wenn sie verwendet werden.  Wenn die Option nicht angegeben wird, lässt [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] nicht konformen Code zu, der Funktionen aufruft, die als `inline` deklariert sind, selbst wenn keine Definition sichtbar ist.  Weitere Informationen finden Sie unter „C\+\+11\-Standard“ in den Abschnitten 3.2 und 7.1.2.  Diese Compileroption wurde in Visual Studio 2013 Update 2 eingeführt.  
  
 Aktualisieren Sie nicht konformen Code, um die Option **\/Zc:inline** zu verwenden.  Dieses Beispiel zeigt, wie die nicht konforme Verwendung einer Inlinefunktionsdeklaration ohne Definition trotzdem kompiliert und verknüpft wird, wenn die Standardoption **\/Zc:inline\-** verwendet wird:  
  
```cpp  
// example.h  
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp  
#pragma once  
  
class Example {  
public:  
   inline void inline_call(); // declared but not defined inline  
   void normal_call();  
   Example() {};  
};  
```  
  
```cpp  
// example.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp  
#include <stdio.h>  
#include "example.h"  
  
void Example::inline_call() {  
   printf("inline_call was called.\n");   
}  
  
void Example::normal_call() {  
   printf("normal_call was called.\n");   
   inline_call(); // with /Zc:inline-, inline_call forced into .obj file  
}  
```  
  
```cpp  
// zcinline.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp  
#include "example.h"  
  
void main() {  
   Example example;  
   example.inline_call(); // normal call when definition unavailable  
}  
```  
  
 Wenn **\/Zc:inline** aktiviert wird, verursacht derselbe Code einen [LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)\-Fehler, weil der Compiler keinen Nicht\-Inlinecodetext für `Example::inline_call` in example.obj ausgibt.  Das führt dazu, dass der Nicht\-Inlineaufruf in `main` ein nicht definiertes externe Symbol referenziert.  
  
 Zur Fehlerbehebung können Sie das Schlüsselwort `inline` aus der Deklaration von `Example::inline_call` entfernen, die Definition von `Example::inline_call` in die Headerdatei verschieben oder die Implementierung von `Example` in main.cpp verschieben.  Im nächsten Beispiel wird die Definition in die Headerdatei verschoben, in der sie für jeden Aufrufer sichtbar ist, der den Header enthält.  
  
```cpp  
// example2.h  
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp  
#pragma once  
#include <stdio.h>  
  
class Example2 {  
public:  
   inline void inline_call() {  
      printf("inline_call was called.\n");   
   }  
   void normal_call();  
   Example2() {};  
};  
```  
  
```cpp  
// example2.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp  
#include "example2.h"  
  
void Example2::normal_call() {  
   printf("normal_call was called.\n");   
   inline_call();   
}  
```  
  
```cpp  
// zcinline2.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp  
#include "example2.h"  
  
void main() {  
   Example2 example2;  
   example2.inline_call(); // normal call when definition unavailable  
}  
```  
  
 Weitere Informationen über Konformitätsprobleme in Visual C\+\+ finden Sie unter [Nicht dem Standard entsprechendes Verhalten](../../cpp/nonstandard-behavior.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie den Ordner **C\/C\+\+** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Befehlszeile** aus.  
  
4.  Ändern Sie die Eigenschaft **Zusätzliche Optionen**, damit sie `/Zc:inline` einschließt, und wählen Sie dann **OK** aus.  
  
## Siehe auch  
 [\/Zc \(Übereinstimmung\)](../../build/reference/zc-conformance.md)