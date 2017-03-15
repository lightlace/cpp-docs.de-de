---
title: "/Zl (Kein Standardbibliotheksname) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/zi"
  - "VC.Project.VCCLCompilerTool.OmitDefaultLibName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zl (Compileroption) [C++]"
  - "Standardbibliotheken, Weglassen von Namen"
  - "Kein Standardbibliotheksname (Compileroption)"
  - "ZI (Compileroption)"
  - "-Zl (Compileroption) [C++]"
ms.assetid: b27d39d0-44d6-498c-84ae-27c1326fee59
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /Zl (Kein Standardbibliotheksname)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit dieser Option wird der Name der Standard\-C\-Laufzeitbibliothek in der OBJ\-Datei weggelassen.  Standardmäßig legt der Compiler den Namen der Bibliothek in der OBJ\-Datei ab, um den Linker zur richtigen Bibliothek zu leiten.  
  
## Syntax  
  
```  
/Zl  
```  
  
## Hinweise  
 Weitere Informationen über die Standardbibliothek finden Sie unter [Laufzeitbibliothek verwenden](../../build/reference/md-mt-ld-use-run-time-library.md).  
  
 Mit **\/Zl** können Sie OBJ\-Dateien kompilieren, die in eine Bibliothek eingefügt werden sollen.  Das Unterdrücken des Bibliotheksnamens spart bei einer einzigen OBJ\-Datei nur wenig Platz ein. In einer Bibliothek, die viele Objektmodule enthält, ist der ingesamt eingesparte Platz jedoch beträchtlich.  
  
 Diese Option ist eine erweiterte Option.  Durch Festlegen dieser Option werden bestimmte Unterstützungen der C\-Laufzeitbibliothek entfernt, die für Ihre Anwendung möglicherweise erforderlich sind. Daher werden bei der Verknüpfung Fehler ausgegeben, wenn die Anwendung von dieser Unterstützung abhängig ist.  Wenn Sie diese Option verwenden, müssen Sie die erforderlichen Komponenten auf eine andere Weise bereitstellen.  
  
 Verwenden Sie [\/NODEFAULTLIB \(Bibliotheken ignorieren\)](../../build/reference/nodefaultlib-ignore-libraries.md). an den Linker, verweisen Bibliotheksreferenzen in allen OBJ\-Dateien zu ignorieren.  
  
 Weitere Informationen finden Sie unter [CRT\-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md).  
  
 Wenn Sie mit **\/Zl** kompilieren, wird `_VC_NODEFAULTLIB` definiert.  Beispiel:  
  
```  
// vc_nodefaultlib.cpp  
// compile with: /Zl  
void Test() {  
   #ifdef _VC_NODEFAULTLIB  
      int i;  
   #endif  
  
   int i;   // C2086  
}  
```  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Erweitert**.  
  
4.  Ändern Sie die Eigenschaft **Standardbibliotheknamen unterdrücken**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitDefaultLibName*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)