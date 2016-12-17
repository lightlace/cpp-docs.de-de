---
title: "Pragma-Direktiven und das __Pragma-Schl&#252;sselwort"
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
  - "#pragma"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#pragma-Direktiven, C/C++"
  - "__pragma-Schlüsselwort"
  - "pragma-Direktiven (#pragma)"
  - "pragma-Direktiven, C/C++"
  - "Pragmas"
  - "Pragmas, C/C++"
  - "Präprozessor"
  - "Präprozessor, Pragmas"
ms.assetid: 9867b438-ac64-4e10-973f-c3955209873f
caps.latest.revision: 20
caps.handback.revision: "20"
ms.author: "corob"
manager: "ghogen"
---
# Pragma-Direktiven und das __Pragma-Schl&#252;sselwort
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pragma\-Direktiven geben computer\- oder betriebssystemspezifische Compilerfunktionen an.  Das `__pragma`\-Schlüsselwort, das für den Microsoft\-Compiler spezifisch ist, ermöglicht das Codieren von Pragma\-Direktiven innerhalb von Makrodefinitionen.  
  
## Syntax  
  
```  
  
      #pragma token-string  
__pragma(token-string)  
```  
  
## Hinweise  
 Jede Implementierung von C und C\+\+ unterstützt mehrere Funktionen, die auf dem Hostcomputer oder Betriebssystem einzigartig sind.  Einige Programme beispielsweise müssen die Speicherbereiche genau kontrollieren, in denen Daten abgelegt werden, oder die Art und Weise steuern, wie bestimmte Funktionen Parameter empfangen.  Die `#pragma`\-Direktive bietet Compilern die Möglichkeit, computer\- und betriebssystemspezifische Funktionen bereitzustellen und dabei die Gesamtkompatibilität mit anderen C\- und C\+\+\-Programmiersprachen beizubehalten.  
  
 Pragmas sind definitionsgemäß computer\- oder betriebssystemspezifisch, und sie sind normalerweise für jeden Compiler unterschiedlich.  Pragmas können in bedingten Anweisungen verwendet werden, um neue Präprozessorfunktionen oder von der Implementierung abhängige Informationen für den Compiler bereitzustellen.  
  
 `token-string` ist eine Reihe von Zeichen, die einem bestimmten Compiler Anweisungen und Argumente gibt, falls vorhanden.  Das Nummernzeichen \(**\#**\) muss das erste Zeichen, das keine Leerstelle ist, in der Zeile sein, die das Pragma enthält. Leerzeichen können das Nummernzeichen und das Wort "Pragma" voneinander trennen.  Nach `#pragma` schreiben Sie beliebigen Text, den das Konvertierungsprogramm als Vorverarbeitungstoken analysieren kann.  Das Argument für `#pragma` unterliegt der Makroerweiterung.  
  
 Wenn der Compiler ein Pragma findet, das er nicht erkennt, gibt er eine Warnung aus und setzt die Kompilierung fort.  
  
 Die Microsoft C\- und C\+\+\-Compiler erkennen die folgenden Pragmas:  
  
||||  
|-|-|-|  
|[alloc\_text](../preprocessor/alloc-text.md)|[auto\_inline](../preprocessor/auto-inline.md)|[bss\_seg](../preprocessor/bss-seg.md)|  
|[check\_stack](../preprocessor/check-stack.md)|[code\_seg](../preprocessor/code-seg.md)|[comment](../preprocessor/comment-c-cpp.md)|  
|[component](../preprocessor/component.md)|[conform](../preprocessor/conform.md) <sup>1</sup>|[const\_seg](../preprocessor/const-seg.md)|  
|[data\_seg](../preprocessor/data-seg.md)|[deprecated](../preprocessor/deprecated-c-cpp.md)|[detect\_mismatch](../preprocessor/detect-mismatch.md)|  
|[fenv\_access](../preprocessor/fenv-access.md)|[float\_control](../preprocessor/float-control.md)|[fp\_contract](../preprocessor/fp-contract.md)|  
|[function](../preprocessor/function-c-cpp.md)|[hdrstop](../preprocessor/hdrstop.md)|[include\_alias](../preprocessor/include-alias.md)|  
|[init\_seg](../preprocessor/init-seg.md) <sup>1</sup>|[inline\_depth](../preprocessor/inline-depth.md)|[inline\_recursion](../preprocessor/inline-recursion.md)|  
|[intrinsic](../preprocessor/intrinsic.md)|[loop](../preprocessor/loop.md) <sup>1</sup>|[make\_public](../preprocessor/make-public.md)|  
|[managed](../preprocessor/managed-unmanaged.md)|[message](../preprocessor/message.md)||  
|[omp](../preprocessor/omp.md)|[once](../preprocessor/once.md)||  
|[optimize](../preprocessor/optimize.md)|[pack](../preprocessor/pack.md)|[pointers\_to\_members](../preprocessor/pointers-to-members.md) <sup>1</sup>|  
|[pop\_macro](../preprocessor/pop-macro.md)|[push\_macro](../preprocessor/push-macro.md)|[region, endregion](../preprocessor/region-endregion.md)|  
|[runtime\_checks](../preprocessor/runtime-checks.md)|[section](../preprocessor/section.md)|[setlocale](../preprocessor/setlocale.md)|  
|[strict\_gs\_check](../preprocessor/strict-gs-check.md)|[unmanaged](../preprocessor/managed-unmanaged.md)|[vtordisp](../preprocessor/vtordisp.md) <sup>1</sup>|  
|[warning](../preprocessor/warning.md)|||  
  
 1.  Wird nur vom C\+\+\-Compiler unterstützt.  
  
## Pragmas und Compileroptionen  
 Einige Pragmas stellen die gleichen Funktionen wie Compileroptionen bereit.  Wenn im Quellcode ein Pragma gefunden wird, überschreibt dieses das Verhalten, das mit der Compileroption angegeben wird.  Wenn Sie beispielsweise [\/Zp8](../build/reference/zp-struct-member-alignment.md) angegeben haben, können Sie diese Compilereinstellung für bestimmte Codeabschnitte mit [pack](../preprocessor/pack.md) überschreiben:  
  
```  
cl /Zp8 ...  
  
<file> - packing is 8  
// ...  
#pragma pack(push, 1) - packing is now 1  
// ...  
#pragma pack(pop) - packing is 8  
</file>  
```  
  
## Das \_\_pragma\(\)\-Schlüsselwort  
 **Microsoft\-spezifisch**  
  
 Der Compiler unterstützt auch das `__pragma`\-Schlüsselwort, das die gleichen Funktionen wie die `#pragma`\-Direktive aufweist, aber in einer Makrodefinition inline verwendet werden kann.  Die `#pragma`\-Direktive kann nicht in einer Makrodefinition verwendet werden, da der Compiler das Nummernzeichen \('\#'\) in der Direktive als [Zeichenfolgenoperator \(\#\)](../preprocessor/stringizing-operator-hash.md) interpretiert.  
  
 Der folgende Beispielcode veranschaulicht die Verwendung des `__pragma`\-Schlüsselworts in einem Makro.  Dieser Code wurde dem mfcdual.h\-Header im ACDUAL\-Beispiel in den Beispielen für die COM\-Unterstützung des Compilers entnommen:  
  
```  
#define CATCH_ALL_DUAL \  
CATCH(COleException, e) \  
{ \  
_hr = e->m_sc; \  
} \  
AND_CATCH_ALL(e) \  
{ \  
__pragma(warning(push)) \  
__pragma(warning(disable:6246)) /*disable _ctlState prefast warning*/ \  
AFX_MANAGE_STATE(pThis->m_pModuleState); \  
__pragma(warning(pop)) \  
_hr = DualHandleException(_riidSource, e); \  
} \  
END_CATCH_ALL \  
return _hr; \  
```  
  
 **Ende Microsoft\-spezifisch**  
  
## Siehe auch  
 [C\/C\+\+\-Präprozessorreferenz](../preprocessor/c-cpp-preprocessor-reference.md)   
 [C\-Pragmas](../c-language/c-pragmas.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)