---
title: "/GR (Laufzeit-Typeninformation aktivieren)"
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
  - "/gr"
  - "VC.Project.VCCLWCECompilerTool.RuntimeTypeInfo"
  - "VC.Project.VCCLCompilerTool.RuntimeTypeInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gr (Compileroption) [C++]"
  - "Aktivieren der Laufzeit-Typinformationen (Compileroption) [C++]"
  - "Gr (Compileroption) [C++]"
  - "-Gr (Compileroption) [C++]"
  - "RTTI-Compileroption"
ms.assetid: d1f9f850-dcec-49fd-96ef-e72d01148906
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "corob"
manager: "ghogen"
---
# /GR (Laufzeit-Typeninformation aktivieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fügt Code hinzu, um Objekttypen während der Laufzeit zu überprüfen.  
  
## Syntax  
  
```  
/GR[-]  
```  
  
## Hinweise  
 Wenn **\/GR** aktiviert ist, definiert der Compiler das `_CPPRTTI` Präprozessormakro.  Standardmäßig ist **\/GR** aktiviert.  **\/GR\-** deaktiviert Laufzeit\-Typeninformation.  
  
 Verwenden Sie **\/GR**, wenn der Compiler einen Objekttyp im Code nicht statisch auflösen kann.  I. d. R. ist die Option **\/GR** erforderlich, wenn im Code [dynamic\_cast\-Operator](../../cpp/dynamic-cast-operator.md) oder [typeid](../../cpp/typeid-operator.md) verwendet wird.  Allerdings vergrößert **\/GR** die .rdata\-Abschnitte im Image.  Wenn **dynamic\_cast** und **typeid** im Code nicht verwendet werden, kann mit **\/GR\-** ggf. ein kleineres Image erzielt werden.  
  
 Weitere Informationen zur Laufzeit\-Typprüfung finden Sie unter [Laufzeit\-Typinformationen](../../cpp/run-time-type-information.md) in der *C\+\+\-Sprachreferenz*.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Sprache**.  
  
4.  Ändern Sie die Eigenschaft **Laufzeit\-Typeninformation aktivieren**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeTypeInfo*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)