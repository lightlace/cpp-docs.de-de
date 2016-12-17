---
title: "/Zc:forScope (&#220;bereinstimmung in for-Schleifenbereich erzwingen)"
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
  - "VC.Project.VCCLCompilerTool.ForceConformanceInForLoopScope"
  - "VC.Project.VCCLWCECompilerTool.ForceConformanceInForLoopScope"
  - "/zc:forScope"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc (Compileroptionen) [C++]"
  - "Übereinstimmung (Compileroptionen)"
  - "Zc (Compileroptionen) [C++]"
  - "-Zc (Compileroptionen) [C++]"
ms.assetid: 3031f02d-3b14-4ad0-869e-22b0110c3aed
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# /Zc:forScope (&#220;bereinstimmung in for-Schleifenbereich erzwingen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verwendet zum Implementieren von Standard\-C\+\+\-Verhalten für [for](../../cpp/for-statement-cpp.md)\-Schleifen mit Microsoft\-Erweiterungen\([\/Ze](../../build/reference/za-ze-disable-language-extensions.md)\).  Standardmäßig ist **\/Zc:forScope** aktiviert.  
  
## Syntax  
  
```  
/Zc:forScope[-]  
```  
  
## Hinweise  
 Die Option **\/Zc:forScope\-** ist veraltet und wird in einer der nächsten Versionen entfernt. Eine Verwendung von **\/Zc:forScope\-** generiert die Veraltungswarnung D9035.  
  
 Standardverhalten bedeutet, den Initialisierer einer **for**\-Schleife nach der **for**\-Schleife den Gültigkeitsbereich verlassen zu lassen. Unter **\/Zc:forScope\-** und [\/Ze](../../build/reference/za-ze-disable-language-extensions.md) bleibt der Initialisierer der **for**\-Schleife im Gültigkeitsbereich, bis der lokale Gültigkeitsbereich endet.  
  
 Der folgende Code wird unter **\/Ze**, aber nicht unter **\/Za** kompiliert:  
  
```cpp  
// zc_forScope.cpp  
// compile by using: cl /Zc:forScope- /Za zc_forScope.cpp  
// C2065, D9035 expected  
int main() {  
    // Compile by using cl /Zc:forScope- zc_forScope.cpp  
    // to compile this non-standard code as-is.  
    // Uncomment the following line to resolve C2065 for /Za.  
    // int i;  
    for (int i = 0; i < 1; i++)  
        ;  
    i = 20;   // i has already gone out of scope under /Za  
}  
```  
  
 Wenn Sie **\/Zc:forScope\-** verwenden, wird die Warnmeldung C4288 \(standardmäßig deaktiviert\) generiert, wenn sich eine Variable aufgrund einer Deklaration, die in einem früheren Gültigkeitsbereich erfolgt ist, im Gültigkeitsbereich befindet. Um dies zu veranschaulichen, entfernen Sie die Zeichen `//` im Beispiel, um `int i` zu deklarieren.  
  
 Sie können das Laufzeitverhalten von **\/Zc:forScope** ändern, indem Sie das [conform](../../preprocessor/conform.md)\-Pragma verwenden.  
  
 Wenn Sie **\/Zc:forScope\-** in einem Projekt verwenden, für das es eine vorhandene PCH\-Datei gibt, wird eine Warnung generiert, wird **\/Zc:forScope\-** ignoriert, und wird die Kompilierung mit der vorhandenen PCH\-Dateien fortgesetzt. Wenn Sie möchten, dass eine neue PCH\-Datei generiert wird, verwenden Sie [\/Yc \(Datei der vorkompilierten Header erstellen\)](../../build/reference/yc-create-precompiled-header-file.md).  
  
 Weitere Informationen über Konformitätsprobleme in Visual C\+\+ finden Sie unter [Nicht dem Standard entsprechendes Verhalten](../../cpp/nonstandard-behavior.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Öffnen Sie im Navigationsbereich die Eigenschaftenseite **Konfigurationseigenschaften**, **C\/C\+\+**, **Sprache**.  
  
3.  Ändern Sie die Eigenschaft **Übereinstimmung in einem For\-Schleifenbereich erzwingen**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForceConformanceInForLoopScope*>.  
  
## Siehe auch  
 [\/Zc \(Übereinstimmung\)](../../build/reference/zc-conformance.md)   
 [\/Za, \/Ze \(Spracherweiterungen deaktivieren\)](../../build/reference/za-ze-disable-language-extensions.md)