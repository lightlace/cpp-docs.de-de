---
title: "/H (L&#228;nge externer Namen beschr&#228;nken) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/h"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/H (Compileroption) [C++]"
  - "Externe Namen"
  - "H (Compileroption) [C++]"
  - "-H (Compileroption) [C++]"
  - "Länge des öffentlichen Namens"
ms.assetid: de701dd3-ed04-4c88-8195-960d2520ec2e
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /H (L&#228;nge externer Namen beschr&#228;nken)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Beschränkt die Länge externer Namen.  
  
## Syntax  
  
```  
/Hnumber  
```  
  
## Argumente  
 `number`  
 die maximal zulässige Länge von externen Namen in einem Programm.  
  
## Hinweise  
 Standardmäßig ist die Länge externer \(öffentlicher\) Namen auf 2.047 Zeichen beschränkt.  Dies gilt für C\- und C\+\+\-Programme.  Mit **\/H** kann die maximal zulässige Länge von Bezeichnern nur herabgesetzt, nicht erhöht werden.  Ein Leerzeichen zwischen **\/H** und `number` ist optional.  
  
 Enthält ein Programm Namen mit mehr Zeichen als in *number* angegeben, werden die zusätzlichen Zeichen nicht beachtet.  Wenn Sie ein Programm ohne **\/H** kompilieren und ein Bezeichner mehr als 2.047 Zeichen enthält, gibt der Compiler den Fehler [Schwerwiegender Fehler C1064](../../error-messages/compiler-errors-1/fatal-error-c1064.md) aus.  
  
 Die beschränkte Länge schließt alle vom Compiler erstellten führenden Unterstriche \(\_\) oder @\-Zeichen ein.  Diese Zeichen gehören zum Bezeichner und nehmen einen wichtigen Platz ein.  
  
-   Der Compiler ergänzt Namen, die mit den Aufrufkonventionen `__cdecl` \(Standard\) und `__stdcall` geändert worden sind, mit einem führenden Unterstrich \(\_\) und Namen, die mit der Aufrufkonvention `__fastcall` geändert worden sind, mit einem führenden @\-Zeichen.  
  
-   Der Compiler hängt Informationen über die Argumentgröße an Namen an, die mit den Aufrufkonventionen \_\_fastcall und \_\_stdcall geändert worden sind, und ergänzt C\+\+\-Namen um Typinformationen.  
  
 **\/H** ist in folgenden Fällen sinnvoll:  
  
-   Beim Erstellen von Programmen in mehreren Sprachen oder portablen Programmen;  
  
-   beim Einsatz von Tools, die die Länge von externen Bezeichnern beschränken;  
  
-   wenn Sie den Platz begrenzen möchten, die Symbole in einem Debugbuild einnehmen.  
  
 Im folgenden Beispiel sehen Sie, wie durch die Verwendung von **\/H** Fehler entstehen können, wenn die Bezeichnerlängen zu sehr beschränkt werden:  
  
```  
// compiler_option_H.cpp  
// compile with: /H5  
// processor: x86  
// LNK2005 expected  
void func1(void);  
void func2(void);  
  
int main() { func1(); }  
  
void func1(void) {}  
void func2(void) {}  
```  
  
 Vorsicht beim Angeben der **\/H**\-Option ist auch aufgrund vordefinierter Compilerbezeichner geboten.  Ist die maximale Bezeichnerlänge zu gering, werden bestimmte vordefinierte Bezeichner nicht aufgelöst, ebenso wie bestimmte Funktionsaufrufe an Bibliotheken.  Wenn beispielsweise die `printf`\-Funktion verwendet wird und beim Kompilieren die Option **\/H5** festgelegt wird, wird das Symbol **\_prin** als Verweis auf `printf` erstellt. Diese kann in der Bibliothek jedoch nicht gefunden werden.  
  
 **\/H** ist nicht mit [\/GL \(Optimierung des ganzen Programms\)](../../build/reference/gl-whole-program-optimization.md) kompatibel.  
  
 **\/H** ist veraltet. Die maximale Länge wurde erhöht, und **\/H** wird nicht mehr benötigt.  Weitere Informationen finden Sie unter [Deprecated Compiler Options in Visual C\+\+ 2005](assetId:///aa59fce3-50b8-4f66-9aeb-ce09a7a84cce).  
  
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