---
title: "/WL (Einzeilige Diagnostik aktivieren)"
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
  - "/wl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/WL (Compileroption) [C++]"
  - "WL (Compileroption) [C++]"
  - "-WL (Compileroption) [C++]"
ms.assetid: 332cadb4-8ea6-45fe-b67d-33ddec1f2c2e
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# /WL (Einzeilige Diagnostik aktivieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Hängt zusätzliche Informationen an eine Fehler\- oder Warnmeldung an.  
  
## Syntax  
  
```  
/WL  
```  
  
## Hinweise  
 An Fehler\- und Warnmeldungen vom C\+\+\-Compiler können sich zusätzliche Informationen anschließen, die standardmäßig in der nächsten Zeile angezeigt werden.  Wenn Sie von der Befehlszeile aus kompilieren, kann die zusätzliche Informationszeile an die Fehler\- oder Warnmeldung angehängt werden.  Das kann erwünscht sein, wenn Sie die Buildausgabe in einer Protokolldatei speichern und diese dann verarbeiten, um alle Fehler und Warnungen zu berücksichtigen.  Die Fehler\- oder Warnmeldung wird durch ein Semikolon von der Zusatzzeile getrennt.  
  
 Nicht alle Fehler\- und Warnmeldungen haben eine zusätzliche Informationszeile.  Der folgende Code generiert einen Fehler mit einer Zusatzzeile mit Informationen. Die Auswirkungen können Sie mithilfe von **\/WL** testen.  
  
```  
// compiler_option_WL.cpp  
// compile with: /WL  
#include <queue>  
int main() {  
   std::queue<int> q;  
   q.fromthecontinuum();   // C2039  
}  
```  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)