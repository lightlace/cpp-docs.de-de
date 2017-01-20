---
title: "/WX (Linkerwarnungen als Fehler behandeln)"
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
  - "/WX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/WX (Linkeroption)"
  - "WX (Linkeroption)"
  - "-WX (Linkeroption)"
ms.assetid: e4ba97c7-93f7-43ae-a4bb-d866790926c9
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# /WX (Linkerwarnungen als Fehler behandeln)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/WX[:NO]  
```  
  
## Hinweise  
 \/WX bewirkt, dass keine Ausgabedatei generiert wird, wenn der Linker eine Warnung generiert.  
  
 Die Option ähnelt der Option **\/WX** für den Compiler. \(Weitere Informationen finden Sie unter [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won \(Warnstufe\)](../../build/reference/compiler-option-warning-level.md).\)  Das Angeben von **\/WX** für die Kompilierung bedeutet jedoch nicht, dass **\/WX** auch in der Linkphase verwendet wird. Sie müssen **\/WX** explizit für jedes Tool angeben.  
  
 Standardmäßig ist **\/WX** nicht aktiv.  Um Linkerwarnungen als Fehler zu behandeln, geben Sie **\/WX** an.  **\/WX:NO** bewirkt dasselbe wie das Weglassen der Option **\/WX**.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Geben Sie die Option im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)