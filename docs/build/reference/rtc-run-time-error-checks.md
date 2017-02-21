---
title: "/RTC (Laufzeitfehler&#252;berpr&#252;fungen) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/rtc"
  - "VC.Project.VCCLCompilerTool.SmallerTypeCheck"
  - "VC.Project.VCCLCompilerTool.UninitializedVariableCheck"
  - "VC.Project.VCCLCompilerTool.StackFrameCheck"
  - "VC.Project.VCCLCompilerTool.BasicRuntimeChecks"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/RTC1-Compileroption [C++]"
  - "/RTCc-Compileroption [C++]"
  - "/RTCs-Compileroption [C++]"
  - "/RTCu (Compileroption) [C++]"
  - "__MSVC_RUNTIME_CHECKS-Makro"
  - "RTC1-Compileroption"
  - "-RTC1-Compileroption [C++]"
  - "RTCc-Compileroption"
  - "-RTCc-Compileroption [C++]"
  - "RTCs-Compileroption"
  - "-RTCs-Compileroption [C++]"
  - "RTCu (Compileroption)"
  - "-RTCu (Compileroption) [C++]"
  - "Laufzeitüberprüfungen, /RTC-Option"
  - "Laufzeitfehler, Fehlerüberprüfung"
  - "Laufzeitfehler, Laufzeitüberprüfungen"
ms.assetid: 9702c558-412c-4004-acd5-80761f589368
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# /RTC (Laufzeitfehler&#252;berpr&#252;fungen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird zur Aktivierung und Deaktivierung der Laufzeitfehlerüberprüfungen in Verbindung mit dem [runtime\_checks](../../preprocessor/runtime-checks.md)\-Pragma verwendet.  
  
## Syntax  
  
```  
/RTC1  
/RTCc  
/RTCs  
/RTCu  
```  
  
## Argumente  
 `1`  
 Äquivalent von **\/RTC**`su`.  
  
 `c`  
 Meldet die Zuweisung eines Werts zu einem kleineren Datentyp und führt zu einem Datenverlust.  Dies ist beispielsweise der Fall, wenn ein Wert vom Typ `short 0x101` einer Variablen vom Typ `char` zugewiesen wird.  
  
 Mit dieser Option werden Situationen gemeldet, in denen Sie eine Verkürzung beabsichtigen, z. B. wenn die ersten acht Bits eines `int`\-Werts als `char` zurückgegeben werden sollen.  Da **\/RTC**`c` einen Laufzeitfehler verursacht, wenn als Ergebnis der Zuweisung Informationen verloren gehen, können Sie die gewünschten Informationen maskieren, um zu vermeiden, dass **\/RTC**`c` zu einem Laufzeitfehler führt.  Beispiel:  
  
```  
#include <crtdbg.h>  
  
char get8bits(int value, int position) {  
   _ASSERT(position < 32);  
   return (char)(value >> position);  
   // Try the following line instead:  
   // return (char)((value >> position) & 0xff);  
}  
  
int main() {  
   get8bits(12341235,3);  
}  
```  
  
 `s`  
 Aktiviert die Laufzeitfehlerüberprüfung für Stapelrahmen wie folgt:  
  
-   Initialisierung lokaler Variablen auf einen Wert ungleich 0.  Dies erleichtert die Identifizierung von Fehlern, die beim Ausführen im Debugmodus nicht auftreten.  Die Wahrscheinlichkeit, dass Stapelvariablen den Wert 0 haben, ist in einem Debugbuild höher als in einem Releasebuild, da der Compiler Stapelvariablen im Releasebuild optimiert.  Nachdem ein Programm auf einen Stapelbereich zugegriffen hat, wird dieser vom Compiler nie auf 0 zurückgesetzt.  Deshalb können nachfolgende, nicht initialisierte Stapelvariablen, die zufällig auf denselben Stapelbereich zugreifen, Werte zurückgeben, die noch vom vorherigen Zugriff auf diesen Stapelspeicherplatz stammen.  
  
-   Erkennung von Über\- und Unterläufen lokaler Variablen z. B. Arrays.  **\/RTC**`s` erkennt keine Überläufe beim Zugreifen auf den Speicher, der sich aus der Compilerauffüllung innerhalb einer Struktur ergibt.  Füllzeichen können bei Verwendung von [align](../../cpp/align-cpp.md), [\/Zp \(Ausrichten des Strukturmembers\)](../../build/reference/zp-struct-member-alignment.md) oder [pack](../../preprocessor/pack.md) auftreten und wenn Strukturelemente so geordnet werden, dass der Compiler Füllzeichen hinzufügen muss.  
  
-   Stapelzeigerüberprüfung, erkennt Beschädigung des Stapelzeigers.  Der Stapelzeiger kann durch Abweichungen einer Aufrufkonvention beschädigt werden.  Dies kann z. B. geschehen, wenn Sie einen Funktionszeiger verwenden und eine Funktion in einer DLL aufrufen, die als [\_\_stdcall](../../cpp/stdcall.md) exportiert wird, den Zeiger für die Funktion jedoch als [\_\_cdecl](../../cpp/cdecl.md) deklarieren.  
  
 `u`  
 Meldet, wenn eine Variable verwendet wird, ohne initialisiert worden zu sein.  So kann beispielsweise eine Anweisung, die den Fehler `C4701` hervorruft, unter **\/RTC**`u` auch einen Laufzeitfehler verursachen.  Jede Anweisung, die den Fehler [Compilerwarnung \(Stufe 1 und Stufe 4\) C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md) hervorruft, verursacht unter **\/RTC**`u` einen Laufzeitfehler.  
  
 Betrachten Sie jedoch das folgende Codefragment:  
  
```  
int a, *b, c;  
if ( 1 )  
b = &a;  
c = a;  // No run-time error with /RTCu  
```  
  
 Wenn die Initialisierung einer Variablen möglich gewesen wäre, wird dies zur Laufzeit nicht von **\/RTC**`u` gemeldet.  Wenn z. B. durch einen Zeiger ein Alias einer Variablen generiert wurde, findet der Compiler die Variable nicht und meldet eine Verwendung ohne Initialisierung.  Eine Variable lässt sich durch die Verwendung ihrer Adresse initialisieren.  Die &\-Operatorarbeiten wie ein Zuweisungsoperator in dieser Situation.  
  
## Hinweise  
 Laufzeitfehlerüberprüfungen bieten Ihnen die Möglichkeit, Fehler im ausgeführten Code zu finden. Weitere Informationen finden Sie unter [Gewusst wie: Verwenden von systemeigenen Laufzeitprüfungen](../Topic/How%20to:%20Use%20Native%20Run-Time%20Checks.md).  
  
 Wenn Sie das Programm in der Befehlszeile mit einer der **\/RTC**\-Compileroptionen kompilieren, treten bei allen [optimize](../../preprocessor/optimize.md)\-Pragmaanweisungen im Code Fehler auf, es werden jedoch keine Fehlermeldungen angezeigt.  Das kommt daher, dass Laufzeitfehlerüberprüfungen in einem Releasebuild \(optimiertem Build\) nicht zulässig sind.  
  
 Sie sollten **\/RTC** für Entwicklungsbuilds verwenden; **\/RTC** sollte nicht für einen Verkaufsversionsbuild verwendet werden.  **\/RTC** kann nicht mit Compiler\-Optimierungen verwendet werden \([\/O\-Optionen \(Code optimieren\)](../../build/reference/o-options-optimize-code.md)\).  Ein mit **\/RTC** erstelltes Programmbild ist etwas größer und langsamer als ein mit **\/Od** erstelltes Bild \(bis zu 5 Prozent langsamer als ein **\/Od**\-Build\).  
  
 Die \_\_MSVC\_RUNTIME\_CHECKS\-Präprozessordirektive wird definiert, wenn Sie eine beliebige **\/RTC**\-Option oder [\/GZ](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md) verwenden.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Codegenerierung**.  
  
4.  Ändern Sie eine oder beide folgenden Eigenschaften: **Vollständige Laufzeitüberprüfungen** oder **Überprüfen von kleineren Typen**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe die Eigenschaften <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BasicRuntimeChecks*> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.SmallerTypeCheck*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [RTC sample](assetId:///b3415b09-f6fd-43dc-8c02-9a910bc2574e)