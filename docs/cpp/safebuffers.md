---
title: Safebuffers | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: safebuffers_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword (C++), safebuffers
- safebuffers __declspec keyword
ms.assetid: 0b0dce14-4523-44d2-8070-5dd0fdabc618
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: eb9541bfc4a94253ac26e118e22c3abb2663a893
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="safebuffers"></a>safebuffers
**Microsoft-spezifisch**  
  
 Weist den Compiler an, keine Pufferüberlauf-Sicherheitsüberprüfungen für eine Funktion einzufügen.  
  
## <a name="syntax"></a>Syntax  
  
```  
__declspec( safebuffers )  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **/GS** -Compileroption bewirkt, dass den Compiler Pufferüberläufe testet, indem sicherheitsüberprüfungen im Stapel eingefügt. Die Typen von Datenstrukturen, die besonders geeignet für sicherheitsüberprüfungen werden in beschriebenen [/GS (Puffer-Sicherheitsüberprüfung)](../build/reference/gs-buffer-security-check.md). Weitere Informationen zu Pufferüberlauf-Erkennung, finden Sie unter [Compiler Security überprüft In Depth](http://go.microsoft.com/fwlink/p/?linkid=7260) auf der MSDN-Website.  
  
 Ein fachmännischer manueller Codereview oder eine externe Analyse kann bestimmen, dass eine Funktion vor einem Pufferüberlauf sicher ist. In diesem Fall können Sie sicherheitsüberprüfungen für eine Funktion unterdrücken, durch Anwenden der `__declspec(safebuffers)` Schlüsselwort, um die Funktionsdeklaration.  
  
> [!CAUTION]
>  Puffer-Sicherheitsüberprüfungen bieten wichtige Sicherheit und haben eine geringfügige Auswirkung auf die Leistung. Daher empfiehlt es sich, sie nicht zu unterdrücken, außer in dem seltenen Fall, in dem die Leistung einer Funktion ein wichtiger Aspekt ist und die Funktion bekanntermaßen sicher ist.  
  
## <a name="inline-functions"></a>Inlinefunktionen  
 Ein *Hauptfunktion* können ein [inlining](inline-functions-cpp.md) Schlüsselwort, um eine Kopie des Einfügen einer *sekundären Funktion*. Wenn die `__declspec(safebuffers)` -Schlüsselwort auf eine Funktion angewendet wird, Pufferüberlauf-Erkennung für diese Funktion unterdrückt wird. Allerdings inlining wirkt sich auf die `__declspec(safebuffers)` Schlüsselwort folgt.  
  
 Nehmen Sie an der **/GS** Compileroption ist für beide Funktionen angegeben, aber die primäre Funktion gibt die `__declspec(safebuffers)` Schlüsselwort. Die Datenstrukturen in der sekundären Funktion machen sie besonders geeignet für Sicherheitsüberprüfungen, und die Funktion unterdrückt diese Überprüfungen nicht. In diesem Fall gilt Folgendes:  
  
-   Geben Sie die ["__forceinline"](inline-functions-cpp.md) -Schlüsselwort in der sekundären Funktion an den Compiler an, die unabhängig von compileroptimierungen Funktion Inline zu erzwingen.  
  
-   Da die sekundäre Funktion für sicherheitsüberprüfungen freigegeben ist, sicherheitsüberprüfungen gelten auch für die primäre Funktion, obwohl er gibt die `__declspec(safebuffers)` Schlüsselwort.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie Sie die `__declspec(safebuffers)` Schlüsselwort.  
  
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
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [__declspec](../cpp/declspec.md)   
 [Stichwörter](../cpp/keywords-cpp.md)   
 [Inline __inline, \__forceinline](inline-functions-cpp.md)   
 [strict_gs_check](../preprocessor/strict-gs-check.md)