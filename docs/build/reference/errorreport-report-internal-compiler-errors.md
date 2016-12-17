---
title: "/errorReport (Meldung &#252;ber interne Compilerfehler)"
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
  - "VC.Project.VCCLCompilerTool.ErrorReporting"
  - "/errorreport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/errorReport (Compileroption) [C++]"
  - "-errorReport (Compileroption) [C++]"
ms.assetid: 819828f8-b0a5-412c-9c57-bf822f17e667
caps.latest.revision: 21
caps.handback.revision: "19"
ms.author: "corob"
manager: "ghogen"
---
# /errorReport (Meldung &#252;ber interne Compilerfehler)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ermöglicht die direkte Weitergabe interner Compilerfehlerinformationen an Microsoft.  
  
## Syntax  
  
```  
/errorReport:[ none | prompt | queue | send ]  
```  
  
## Argumente  
 **none**  
 Berichte zu internen Compilerfehlern werden nicht gesammelt oder an Microsoft gesendet.  
  
 **prompt**  
 Sie werden aufgefordert, einen Bericht zu senden, wenn Sie einen internen Compilerfehler empfangen.  **prompt** ist der Standard, wenn eine Anwendung in der Entwicklungsumgebung kompiliert wird.  
  
 **queue**  
 Der Fehlerbericht wird in die Warteschleife eingereiht.  Wenn Sie sich mit Administratorberechtigung anmelden, wird ein Fenster angezeigt, über das Sie alle Fehler seit der letzten Anmeldung melden können \(Sie werden nicht öfter als alle drei Tage einmal aufgefordert, Fehlerberichte zu versenden\).  **queue** ist der Standard, wenn eine Anwendung in einer Eingabeaufforderung kompiliert wird.  
  
 **send**  
 Berichte über interne Compilerfehler werden automatisch an Microsoft gesendet.  Um diese Option zu aktivieren, müssen Sie zuerst der Datensammlungsrichtlinie von Microsoft zustimmen.  Wenn Sie **\/errorReport:send** das erste Mal auf einem Computer angeben, werden Sie in einer Compilermeldung auf eine Website mit der Datensammlungsrichtlinie von Microsoft verwiesen.  
  
 Diese Option hängt von den Registrierungseinstellungen ab.  Weitere Informationen darüber, wie die entsprechenden Werte in der Registrierung, finden Sie auf [Verwenden von automatischen Fehlerbericht in Visual Studio 2008\-Befehlszeilentools einschaltet](http://go.microsoft.com/fwlink/?LinkID=184695) der MSDN\-Website festlegt.  
  
## Hinweise  
 Ein interner Compilerfehler tritt auf, wenn der Compiler eine Quellcodedatei nicht verarbeiten kann.  Bei Auftreten eines internen Compilerfehlers wird vom Compiler keine Ausgabedatei oder hilfreiche Analyse erstellt, die Sie zum Beheben des Fehlers im Code verwenden können.  
  
 In früheren Versionen wurden Sie beim Auftreten eines internen Compilerfehlers aufgefordert, das Problem dem Microsoft\-Produktsupport zu melden.  Mit **\/errorReport** können ICE\-Informationen direkt an Microsoft gesendet werden.  Die Fehlerberichte können dazu beitragen, zukünftige Compilerversionen zu verbessern.  
  
 Ob Benutzer Berichte versenden können, ist von den Computer\- und den Benutzerberechtigungen abhängig.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Weitere Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Erweitert**.  
  
4.  Ändern Sie die Eigenschaft **Problembericht**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ErrorReporting*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)