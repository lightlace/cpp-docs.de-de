---
title: -ErrorReport (Meldung interne Compilerfehler) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.ErrorReporting
- /errorreport
dev_langs:
- C++
helpviewer_keywords:
- /errorReport compiler option [C++]
- -errorReport compiler option [C++]
ms.assetid: 819828f8-b0a5-412c-9c57-bf822f17e667
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67e87143d31de98039f5d679c102a5815dd87abb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377247"
---
# <a name="errorreport-report-internal-compiler-errors"></a>/errorReport (Meldung über interne Compilerfehler)
Ermöglicht es Ihnen, Informationen über interne Compilerfehler (ICE) direkt an Microsoft zu senden.  
  
## <a name="syntax"></a>Syntax  
  
```  
/errorReport:[ none | prompt | queue | send ]  
```  
  
## <a name="arguments"></a>Argumente  
 **none**  
 Berichte zu internen Compilerfehlern werden nicht gesammelt oder an Microsoft gesendet.  
  
 **Aufforderung**  
 Sie werden aufgefordert, einen Bericht zu senden, wenn Sie einen internen Compilerfehler empfangen. **Eingabeaufforderung** ist die Standardeinstellung, wenn eine Anwendung in der Entwicklungsumgebung kompiliert wird.  
  
 **Warteschlange**  
 Der Fehlerbericht wird in die Warteschlange gesetzt. Wenn Sie sich mit Administratorrechten anmelden, wird ein Fenster angezeigt, sodass Sie alle Fehler seit der letzten Ausführung melden können, wurden Sie sich angemeldet (nicht werden Sie aufgefordert, Fehlerberichte Senden von mehr als einmal alle drei Tage). **Warteschlange** ist die Standardeinstellung, wenn eine Anwendung in einer Befehlszeile kompiliert wird.  
  
 **Senden**  
 Automatisch Berichte über interne Compilerfehler an Microsoft gesendet, sofern reporting durch die Einstellungen für das Windows-Fehlerberichterstattung aktiviert ist.  
  
## <a name="remarks"></a>Hinweise  
 Ein interner Compilerfehler (ICE) entsteht, wenn der Compiler eine Quellcodedatei nicht verarbeiten kann. Tritt ein ICE auf, erzeugt der Compiler keine Ausgabedatei oder eine hilfreiche Diagnose, die Sie verwenden können, um Ihren Code zu beheben.  
  
 In früheren Versionen wurden Sie bei einer Compilerfehlers aufgefordert, rufen Sie die Microsoft-Produktsupport, um das Problem zu melden. Mit **/errorreport**, können Sie ICE-Informationen direkt an Microsoft bereitstellen. Die Fehlerberichte können dabei helfen, zukünftige Compilerversionen zu verbessern.  
  
 Die Fähigkeit eines Benutzers zum Senden von Berichten hängt vom Computer und den Benutzerberechtigungen ab.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die **erweitert** Eigenschaftenseite.  
  
4.  Ändern der **-Fehlerberichterstattung** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ErrorReporting%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)