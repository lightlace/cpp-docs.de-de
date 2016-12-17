---
title: "/Os, /Ot (Kompakten Code bevorzugen, Schnellen Code bevorzugen)"
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
  - "VC.Project.VCCLWCECompilerTool.FavorSizeOrSpeed"
  - "/os"
  - "VC.Project.VCCLCompilerTool.FavorSizeOrSpeed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Os (Compileroption) [C++]"
  - "/Ot (Compileroption) [C++]"
  - "Schneller Code"
  - "Schnellen Code bevorzugen (Compileroption) [C++]"
  - "Kompakten Code bevorzugen (Compileroption) [C++]"
  - "Os (Compileroption) [C++]"
  - "-Os (Compileroption) [C++]"
  - "Ot (Compileroption) [C++]"
  - "-Ot (Compileroption) [C++]"
  - "Kompakter Computercode"
ms.assetid: 9a340806-fa15-4308-892c-355d83cac0f2
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# /Os, /Ot (Kompakten Code bevorzugen, Schnellen Code bevorzugen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Minimiert oder maximiert die Größe von EXE\- und DLL\-Dateien.  
  
## Syntax  
  
```  
/Os  
/Ot  
```  
  
## Hinweise  
 **\/Os** \(Kompakten Code bevorzugen\) minimiert die Größe von EXE\- und DLL\-Dateien durch die Anweisung an den Compiler, Programmgröße gegenüber Geschwindigkeit zu bevorzugen.  Der Compiler kann viele C\- und C\+\+\-Konstrukte zu funktional ähnlichen Maschinencodefolgen reduzieren.  Gelegentlich muss dabei zwischen Größe und Geschwindigkeit abgewogen werden.  Mit den Optionen **\/Os** und **\/Ot** können Sie eine Präferenz angeben:  
  
 **\/Ot** \(Schnellen Code bevorzugen\) maximiert die Geschwindigkeit von EXE\- und DLL\-Dateien durch die Anweisung an den Compiler, Geschwindigkeit gegenüber Programmgröße zu bevorzugen. \(Das ist die Standardeinstellung.\) Der Compiler kann viele C\- und C\+\+\-Konstrukte zu funktional ähnlichen Maschinencodefolgen reduzieren.  Gelegentlich muss dabei zwischen Größe und Geschwindigkeit abgewogen werden.  Die \/Ot\-Option ist durch die Geschwindigkeit maximieren \([\/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)\)\-Option impliziert.  Bei der **\/O2**\-Option werden verschiedene Optionen kombiniert, um sehr schnellen Code zu erzeugen.  
  
 Wenn Sie **\/Os** oder **\/Ot** verwenden, müssen Sie auch [\/Og](../../build/reference/og-global-optimizations.md) angeben, um den Code zu optimieren.  
  
> [!NOTE]
>  Informationen, die bei Testläufen für die Profilerstellung erfasst wurden, überschreiben Optimierungen, die sonst bei Angabe von **\/Ob**, **\/Os** oder **\/Ot** aktiv wären.  Weitere Informationen finden Sie unter [Profilgesteuerte Optimierungen \(PGO\)](../../build/reference/profile-guided-optimizations.md).  
  
 **x86\-spezifisch**  
  
 Das nachfolgende Codebeispiel zeigt den Unterschied zwischen den Optionen Kompakten Code bevorzugen \(**\/Os**\) und Schnellen Code bevorzugen \(**\/Ot**\):  
  
> [!NOTE]
>  Im Folgenden wird das erwartete Verhalten bei Verwendung von **\/Os** oder **\/Ot** beschrieben.  Zwischen den einzelnen Versionen kann das Compilerverhalten in Bezug auf die Optimierung des unten aufgeführten Codes jedoch variieren.  
  
```  
/* differ.c  
  This program implements a multiplication operator  
  Compile with /Os to implement multiply explicitly as multiply.  
  Compile with /Ot to implement as a series of shift and LEA instructions.  
*/  
int differ(int x)  
{  
    return x * 71;  
}  
```  
  
 Der nachfolgende Ausschnitt aus dem Maschinencode zeigt, dass der Compiler den Multiplikationsausdruck in der return\-Anweisung explizit als eine Multiplikation implementiert, um eine kurze, aber langsamere Codefolge zu erzeugen, wenn bei der Kompilierung von DIFFER.c kompakter Code bevorzugt wird \(**\/Os**\):  
  
```  
mov    eax, DWORD PTR _x$[ebp]  
imul   eax, 71                  ; 00000047H  
```  
  
 Wenn bei der Kompilierung von DIFFER.c dagegen Geschwindigkeit bevorzugt wird \(**\/Ot**\), implementiert der Compiler den Multiplikationsausdruck in der return\-Anweisung als eine Folge von Schiebe\- und `LEA`\-Anweisungen, um eine schnelle, jedoch längere Codefolge zu erzeugen:  
  
```  
mov    eax, DWORD PTR _x$[ebp]  
mov    ecx, eax  
shl    eax, 3  
lea    eax, DWORD PTR [eax+eax*8]  
sub    eax, ecx  
```  
  
 **END x86\-spezifisch**  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Optimierung**.  
  
4.  Ändern Sie die Eigenschaft **Größe oder Geschwindigkeit bevorzugen**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.FavorSizeOrSpeed*>.  
  
## Siehe auch  
 [\/O\-Optionen \(Code optimieren\)](../../build/reference/o-options-optimize-code.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)