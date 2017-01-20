---
title: "/INCLUDE (Symbolverweise erzwingen)"
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
  - "/include"
  - "VC.Project.VCLinkerTool.ForceSymbolReferences"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/INCLUDE (Linkeroption)"
  - "Symbolverweise erzwingen (Linkeroption)"
  - "INCLUDE (Linkeroption)"
  - "-INCLUDE (Linkeroption)"
  - "Erzwingen von Symbolverweisen (Linkeroption)"
  - "Symbole, Hinzufügen zur Symboltabelle"
ms.assetid: 4a039677-360a-480f-bd0b-448e239b449c
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# /INCLUDE (Symbolverweise erzwingen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/INCLUDE:symbol  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `symbol`  
 ein der Symboltabelle hinzuzufügendes Symbol.  
  
## Hinweise  
 Die \/INCLUDE\-Option weist den Linker an, der Symboltabelle ein bestimmtes Symbol hinzuzufügen.  
  
 Um mehrere Symbole festzulegen, geben Sie ein Komma \(,\), ein Semikolon \(;\) oder ein Leerzeichen zwischen den Symbolnamen ein.  In der Befehlszeile sollten Sie für jedes Symbol **\/INCLUDE**:*Symbol* angeben.  
  
 Der Linker löst `symbol` auf, indem das Objekt, das die Symboldefinition enthält, zum Programm hinzugefügt wird.  Auf diese Weise können Sie ein Bibliotheksobjekt einschließen, das sonst nicht in das Programm eingebunden werden würde.  
  
 Durch Bestimmen eines Symbols mit dieser Option wird das automatische Löschen dieses Symbols durch die Option [\/OPT:REF](../../build/reference/opt-optimizations.md) überschrieben.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Eingabe**.  
  
4.  Ändern Sie die Eigenschaft **Symbolverweise erzwingen**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ForceSymbolReferences*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)