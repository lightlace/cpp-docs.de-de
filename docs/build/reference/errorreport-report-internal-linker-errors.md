---
title: "/ERRORREPORT (Weiterleiten von internen Linkerfehlern)"
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
  - "/ERRORREPORT"
  - "VC.Project.VCLinkerTool.ErrorReporting"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ERRORREPORT (Linkeroption)"
  - "ERRORREPORT (Linkeroption)"
  - "-ERRORREPORT (Linkeroption)"
ms.assetid: f5fab595-a2f1-4eb0-ab5c-1c0fbd3d8c28
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# /ERRORREPORT (Weiterleiten von internen Linkerfehlern)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/errorReport:[ none | prompt | queue | send ]  
```  
  
## Hinweise  
 Ermöglicht die direkte Weitergabe interner Compilerfehlerinformationen an Microsoft.  
  
 Die Option **\/errorReport:send** versucht, Fehlerinformationen automatisch an Microsoft zu senden, aber Erfolg hängt von den Registrierungseinstellungen ab.  Weitere Informationen dazu, wie Sie die entsprechenden Werte in der Registrierung, finden Sie auf [Verwenden von automatischen Fehlerbericht in Visual Studio 2008\-Befehlszeilentools einschaltet](http://go.microsoft.com/fwlink/?LinkID=184695) der MSDN\-Website festlegt.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Weitere Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **Konfigurationseigenschaften**.  
  
3.  Klicken Sie auf den Ordner **Linker**.  
  
4.  Klicken Sie auf die Eigenschaftenseite **Erweitert**.  
  
5.  Ändern Sie die Eigenschaft **Problembericht**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ErrorReporting*>.  
  
## Siehe auch  
 [\/errorReport \(Meldung über interne Compilerfehler\)](../../build/reference/errorreport-report-internal-compiler-errors.md)   
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)