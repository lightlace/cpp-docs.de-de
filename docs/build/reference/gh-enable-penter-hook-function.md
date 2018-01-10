---
title: -Gh (_penter-Hookfunktion aktivieren) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _penter
dev_langs: C++
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _penter function
- -Gh compiler option [C++]
ms.assetid: 1510a082-8a0e-486e-a309-6add814b494f
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dec38a8822bb8a330c4dccff9833780ea3a0a45d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="gh-enable-penter-hook-function"></a>/Gh (_penter-Hookfunktion aktivieren)
Bewirkt, dass einen Aufruf der `_penter` Funktion am Anfang jeder Methode oder Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Gh  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `_penter` Funktion ist nicht Teil einer Bibliothek, und es liegt bei Ihnen, senden eine Definition für `_penter`.  
  
 Wenn Sie explizit aufrufen möchten `_penter`, Sie müssen sich nicht um einen Prototyp bereitzustellen. Die Funktion muss angezeigt werden, als ob er den folgenden Prototyp hatte und muss den Inhalt aller Register auf Eintrag push und pop unverändert Inhalt beim Beenden:  
  
```  
void __declspec(naked) _cdecl _penter( void );  
```  
  
 Diese Deklaration ist nicht für 64-Bit-Projekte verfügbar.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden code, bei der Kompilierung mit **/GH**, zeigt wie `_penter` wird zweimal aufgerufen, einmal beim Eingeben der Funktion `main` einmal bei der Eingabe der Funktion `x`.  
  
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
  
```Output  
In a function!  
In a function!  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)