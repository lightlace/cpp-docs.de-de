---
title: -Os -Ot (kompakten Code bevorzugen, schnellen Code bevorzugen) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.FavorSizeOrSpeed
- /os
- VC.Project.VCCLCompilerTool.FavorSizeOrSpeed
dev_langs:
- C++
helpviewer_keywords:
- favor fast code compiler option [C++]
- /Os compiler option [C++]
- Ot compiler option [C++]
- /Ot compiler option [C++]
- small machine code
- -Ot compiler option [C++]
- fast code
- favor small code compiler option [C++]
- Os compiler option [C++]
- -Os compiler option [C++]
ms.assetid: 9a340806-fa15-4308-892c-355d83cac0f2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 02ce4b7d5c9617a88450fd90b4ac6c75d41148ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="os-ot-favor-small-code-favor-fast-code"></a>/Os, /Ot (Kompakten Code bevorzugen, Schnellen Code bevorzugen)
Minimiert oder maximiert die Größe des EXEs und DLLs.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Os  
/Ot  
```  
  
## <a name="remarks"></a>Hinweise  
 **/ OS** (kompakten Code bevorzugen) minimiert die Größe des EXEs und DLLs durch weist den Compiler an, Geschwindigkeit Größe vorzuziehen. Der Compiler kann viele C- und C++-Konstrukte mit ähnlichen Sequenzen von Computercode reduzieren. Gelegentlich abgewogen Größe und Geschwindigkeit. Die **/OS** und **/Ot** Optionen können Sie eine Präferenz angeben:  
  
 **/ Ot** (bevorzugen, schnellen Code bevorzugen) maximiert die Geschwindigkeit der EXEs und DLLs, indem Sie weist den Compiler an Größe Geschwindigkeit vorzuziehen. (Dies ist die Standardeinstellung.) Der Compiler kann viele C- und C++-Konstrukte mit ähnlichen Sequenzen von Computercode reduzieren. In einigen Fällen abgewogen Größe und Geschwindigkeit. Die Option/Ot wird impliziert, durch die Geschwindigkeit maximieren ([/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)) Option. Die **/O2** Option kombiniert mehrere Optionen zum Erzeugen von sehr schnellen Codes.  
  
 Bei Verwendung von **/OS** oder **/Ot**, dann müssen Sie auch angeben [/Og](../../build/reference/og-global-optimizations.md) um den Code zu optimieren.  
  
> [!NOTE]
>  Informationen, die vom Test profilerstellungsausführungen gesammelt werden, überschreiben Optimierungen, die andernfalls geltende wäre, wenn Sie angeben, **tatsächlich**, **/OS**, oder **/Ot**. Weitere Informationen [Profilgesteuerte Optimierung](../../build/reference/profile-guided-optimizations.md).  
  
 **X86 bestimmte**  
  
 Der folgende Beispielcode zeigt den Unterschied zwischen den kompakten Code bevorzugen (**/OS**) Optionen und schnellen Code bevorzugen (**/Ot**) Option:  
  
> [!NOTE]
>  Im folgenden wird das erwartete Verhalten beschrieben, bei Verwendung **/OS** oder **/Ot**. Allerdings Compilerverhalten von Version zu Version möglicherweise verschiedene Optimierungen für den folgenden Code.  
  
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
  
 Wie im Fragment von Computercode unten dargestellt, wenn DIFFER.c kompiliert wird für die Größe (**/OS**), implementiert der Compiler die multiply-Ausdruck in der return-Anweisung explizit als ein multiplizieren, um eine kurze, jedoch langsamer Codesequenz zu erzeugen:  
  
```  
mov    eax, DWORD PTR _x$[ebp]  
imul   eax, 71                  ; 00000047H  
```  
  
 Klicken Sie alternativ Wenn DIFFER.c für Geschwindigkeit kompiliert wird (**/Ot**), implementiert der Compiler die multiply-Ausdruck in der return-Anweisung als eine Reihe von UMSCHALT und `LEA` Anweisungen, um eine schnelle, aber länger Codesequenz zu erzeugen:  
  
```  
mov    eax, DWORD PTR _x$[ebp]  
mov    ecx, eax  
shl    eax, 3  
lea    eax, DWORD PTR [eax+eax*8]  
sub    eax, ecx  
```  
  
 **END X86 bestimmte**  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die **Optimierung** Eigenschaftenseite.  
  
4.  Ändern der **Größe oder Geschwindigkeit bevorzugen** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.FavorSizeOrSpeed%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [/ O-Optionen (Code optimieren)](../../build/reference/o-options-optimize-code.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)