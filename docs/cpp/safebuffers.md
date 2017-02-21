---
title: "safebuffers | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "safebuffers"
  - "safebuffers_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec-Schlüsselwort (C++), safebuffers"
  - "safebuffers __declspec-Schlüsselwort"
ms.assetid: 0b0dce14-4523-44d2-8070-5dd0fdabc618
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# safebuffers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Weist den Compiler an, keine Pufferüberlauf\-Sicherheitsüberprüfungen für eine Funktion einzufügen.  
  
## Syntax  
  
```  
__declspec( safebuffers )  
```  
  
## Hinweise  
 Die **\/GS**\-Compileroption bewirkt, dass der Compiler Pufferüberläufe testet, indem Sicherheitsüberprüfungen im Stapel eingefügt werden.  Die Typen der Datenstrukturen, die für Sicherheitsüberprüfungen freigegeben sind, werden in [\/GS \(Puffer\-Sicherheitsüberprüfung\)](../build/reference/gs-buffer-security-check.md) beschrieben.  Weitere Informationen zur Pufferüberlauferkennung finden Sie unter [Compiler\-Sicherheitsüberprüfungen im Detail](http://go.microsoft.com/fwlink/?linkid=7260) auf der MSDN\-Website.  
  
 Eine fachmännische manuelle Codeüberprüfung oder externe Analyse kann bestimmten, dass eine Funktion vor einem Pufferüberlauf sicher ist.  In diesem Fall können Sie Sicherheitsüberprüfungen für eine Funktion unterdrücken, indem Sie das \_\_`declspec(safebuffers)`\-Schlüsselwort auf die Funktionsdeklaration anwenden.  
  
> [!CAUTION]
>  Puffer\-Sicherheitsüberprüfungen bieten wichtige Sicherheit und haben eine geringfügige Auswirkung auf die Leistung.  Daher empfiehlt es sich, sie nicht zu unterdrücken, außer in dem seltenen Fall, in dem die Leistung einer Funktion ein wichtiger Aspekt ist und die Funktion bekanntermaßen sicher ist.  
  
## Inlinefunktionen  
 Eine *primäre Funktion* kann ein [Inlining](../misc/inline-inline-forceinline.md)\-Schlüsselwort verwenden, um eine Kopie einer *sekundären Funktion* einzufügen.  Wenn das \_\_`declspec(safebuffers)` \-Schlüsselwort auf eine Funktion angewendet wird, wird die Pufferüberlauferkennung für diese Funktion unterdrückt.  Allerdings wirkt sich das Inlining auf das \_\_`declspec(safebuffers)` \- Schlüsselwort in folgender Weise aus.  
  
 Angenommen, die **\/GS**\-Compileroption ist für beide Funktionen angegeben, aber die primäre Funktion gibt das \_\_`declspec(safebuffers)` \-Schlüsselwort an.  Die Datenstrukturen in der sekundären Funktion machen sie besonders geeignet für Sicherheitsüberprüfungen, und die Funktion unterdrückt diese Überprüfungen nicht.  In diesem Fall gilt Folgendes:  
  
-   Geben Sie das [\_\_forceinline](../misc/inline-inline-forceinline.md)\-Schlüsselwort in der sekundären Funktion an, damit der Compiler diese Funktion unabhängig von den Compileroptimierungen inline ausführt.  
  
-   Da die sekundäre Funktion für Sicherheitsüberprüfungen freigegeben ist, werden auch Sicherheitsüberprüfungen für die primäre Funktion durchgeführt, obwohl durch sie das \_\_`declspec(safebuffers)` \-Schlüsselwort angegeben wird.  
  
## Beispiel  
 Im folgenden Code wird die Verwendung des \_\_`declspec(safebuffers)` \-Schlüsselworts veranschaulicht.  
  
```  
// compile with: /c /GS  
typedef struct {  
    int x[20];  
} BUFFER;  
static int checkBuffers() {  
    BUFFER cb;  
    // Use the buffer...  
    return 0;  
};  
static __declspec(safebuffers)   
    int noCheckBuffers() {  
    BUFFER ncb;  
    // Use the buffer...  
    return 0;  
}  
int wmain() {  
    checkBuffers();  
    noCheckBuffers();  
    return 0;  
}  
```  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [inline, \_\_inline, \_\_forceinline](../misc/inline-inline-forceinline.md)   
 [strict\_gs\_check](../preprocessor/strict-gs-check.md)