---
title: "-Gs (Stapel-Überprüfungsaufrufe kontrollieren) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /GS
dev_langs: C++
helpviewer_keywords:
- disabling stack probes
- GS compiler option [C++]
- /GS compiler option [C++]
- stack, stack probes
- stack probes
- -GS compiler option [C++]
- stack checking calls
ms.assetid: 40daed7c-f942-4085-b872-01e12b37729e
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4c957ff59976406609a88bfbfe3e1f51af44d6c6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="gs-control-stack-checking-calls"></a>/Gs (Stapel-Überprüfungsaufrufe kontrollieren)
Steuert Stapelüberprüfungen  
  
## <a name="syntax"></a>Syntax  
  
```  
/Gs[size]  
```  
  
## <a name="arguments"></a>Argumente  
 `size`  
 (Optional) Die Anzahl von Bytes, die von lokalen Variablen belegt werden können, bevor eine Stapelüberprüfung initiiert wird. Wenn die **/GS** Option angegeben wird, ohne eine `size` Argument, es ist derselbe, als wenn **/Gs0**,  
  
## <a name="remarks"></a>Hinweise  
 Eine Stapelüberprüfung ist eine Codesequenz, die der Compiler in jeden Funktionsaufruf einfügt. Sobald die Stapelüberprüfung initiiert ist, belegt sie im Speicher so viel Platz, wie zum Speichern der lokalen Variablen der Funktion nötig ist.  
  
 Wenn durch eine Funktion mehr als `size` Bytes an Stapelspeicher für lokale Variablen anfordert, wird für diese Funktion die Stapelüberprüfung initiiert. Standardmäßig generiert der Compiler Code, der eine Stapelüberprüfung initiiert, wenn für eine Funktion mehr als eine Seite Stapelspeicher erforderlich ist. Dies ist gleichbedeutend mit einer Compileroption **/Gs4096** für X86, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], und ARM-Plattformen. Mit diesem Wert sind eine Anwendung und der Speichermanager von Windows in der Lage, den für den Programmstapel reservierten Arbeitsspeicher zur Laufzeit dynamisch zu erhöhen.  
  
> [!NOTE]
>  Der Standardwert von **/Gs4096** ermöglicht es den Programmstapel von Anwendungen für Windows zur Laufzeit ordnungsgemäß vergrößert. Wir empfehlen, den Standardwert nur dann zu ändern, wenn Sie genau wissen, warum Sie ihn ändern müssen.  
  
 Für einige Programme, beispielsweise virtuelle Gerätetreiber, ist dieser Standardmechanismus zum Vergrößern des Stapels nicht erforderlich. In solchen Fällen sind die Stapelüberprüfungen nicht erforderlich, und Sie können verhindern, dass der Compiler diese generiert, indem Sie `size` auf einen Wert festlegen, der so groß ist, wie ihn keine Funktion zum Speichern ihrer lokalen Variablen benötigt. Darf kein Leerzeichen zwischen **/GS** und `size`.  
  
 **/ Gs0** aktiviert stapelüberprüfungen für jeden Funktionsaufruf, der Speicher für lokale Variablen benötigt. Das kann sich negativ auf die Leistung auswirken.  
  
 Können Sie stapelüberprüfungen ein- oder ausschalten aktivieren, indem Sie mithilfe von [Check_stack](../../preprocessor/check-stack.md). **/ GS** und `check_stack` Pragma haben keine Auswirkungen auf standardmäßige C-Bibliotheksroutinen; sie wirken sich auf nur die Funktionen, die Sie kompilieren.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **C/C++-** Ordner.  
  
3.  Wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)