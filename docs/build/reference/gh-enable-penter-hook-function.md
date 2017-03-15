---
title: "/Gh (_penter-Hookfunktion aktivieren) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_penter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gh (Compileroption) [C++]"
  - "_penter-Funktion"
  - "Gh (Compileroption) [C++]"
  - "-Gh (Compileroption) [C++]"
ms.assetid: 1510a082-8a0e-486e-a309-6add814b494f
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# /Gh (_penter-Hookfunktion aktivieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Führt zu einem Aufruf der `_penter`\-Funktion zu Beginn jeder Methode oder Funktion.  
  
## Syntax  
  
```  
/Gh  
```  
  
## Hinweise  
 Die `_penter`\-Funktion gehört zu keiner Bibliothek; Sie müssen daher selbst eine Definition für `_penter` angeben.  
  
 Wenn Sie nicht die Absicht haben, \_penter explizit aufzurufen, brauchen Sie keinen Prototypen bereitzustellen.  Die Funktion muss so angezeigt werden, als hätte sie den folgenden Prototypen, und sie muss den Inhalt aller Register beim Eintritt auf den Stapel legen und den unveränderten Inhalt beim Austritt vom Stapel holen:  
  
```  
void __declspec(naked) _cdecl _penter( void );  
```  
  
 Diese Deklaration ist nicht für 64\-Bit\-Projekte verfügbar.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Beispiel  
 Im folgenden Codebeispiel wird dargestellt, wie beim Kompilieren mit **\/Gh** die `_penter`\-Funktion zweimal aufgerufen wird: einmal zu Beginn der `main`\-Funktion und einmal zu Beginn der `x`\-Funktion.  
  
```  
// Gh_compiler_option.cpp  
// compile with: /Gh  
// processor: x86  
#include <stdio.h>  
void x() {}  
  
int main() {  
   x();  
}  
  
extern "C" void __declspec(naked) _cdecl _penter( void ) {  
   _asm {  
      push eax  
      push ebx  
      push ecx  
      push edx  
      push ebp  
      push edi  
      push esi  
    }  
  
   printf_s("\nIn a function!");  
  
   _asm {  
      pop esi  
      pop edi  
      pop ebp  
      pop edx  
      pop ecx  
      pop ebx  
      pop eax  
      ret  
    }  
}  
```  
  
  **In einer Funktion\!**  
**In einer Funktion\!**   
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)