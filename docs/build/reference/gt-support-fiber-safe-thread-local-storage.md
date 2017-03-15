---
title: "/GT (Fiber-sicheren lokalen Thread-Speicher unterst&#252;tzen) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.EnableFiberSafeOptimizations"
  - "/gt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GT (Compileroption) [C++]"
  - "Fiber-sicherer statischer lokaler Threadspeicher (Compileroption) [C++]"
  - "GT (Compileroption) [C++]"
  - "-GT (Compileroption) [C++]"
  - "Statischer lokaler Threadspeicher und Fiber-Sicherheit"
  - "Lokaler Threadspeicher"
ms.assetid: 071fec79-c701-432b-9970-457344133159
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /GT (Fiber-sicheren lokalen Thread-Speicher unterst&#252;tzen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Option unterstützt Fiber\-Sicherheit für Daten, die mit statischem lokalen Threadspeicher zugewiesen werden, d. h. mit `__declspec(thread)` zugewiesene Daten.  
  
## Syntax  
  
```  
/GT  
```  
  
## Hinweise  
 Auf als `__declspec(thread)` deklarierte Daten wird über einen Array des lokalen Threadspeichers \(TLS\-Array\) verwiesen.  Der TLS\-Array enthält Adressen, die das System für jeden Thread verwaltet.  Jede Adresse in diesem Array gibt den Speicherort von Daten im lokalen Thread\-Speicher an.  
  
 Ein Fiber ist ein elementares Objekt, das aus einem Stapel und einem Registerkontext besteht und für verschiedene Threads vorgesehen werden kann.  Ein Fiber kann auf einem beliebigen Thread ausgeführt werden.  Da ein Fiber ausgelagert und später auf einem anderen Thread neu gestartet werden könnte, darf die Adresse des TLS\-Arrays nicht gepuffert oder über Funktionsaufrufe hinweg als gemeinsamer Teilausdruck optimiert werden \(weitere Informationen finden Sie in den Erläuterungen zur [\/Og \(Globale Optimierungen\)](../../build/reference/og-global-optimizations.md)\-Option\).  **\/GT** verhindert diese Optimierungen.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Optimierung**.  
  
4.  Ändern Sie die Eigenschaft **Fiber\-sichere Optimierungen aktivieren**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFiberSafeOptimizations*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)