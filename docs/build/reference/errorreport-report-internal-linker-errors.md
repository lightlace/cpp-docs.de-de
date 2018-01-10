---
title: -ERRORREPORT (internen Linkerfehlern) | Microsoft Docs
ms.custom: 
ms.date: 12/28/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /ERRORREPORT
- VC.Project.VCLinkerTool.ErrorReporting
dev_langs: C++
helpviewer_keywords:
- /ERRORREPORT linker option
- ERRORREPORT linker option
- -ERRORREPORT linker option
ms.assetid: f5fab595-a2f1-4eb0-ab5c-1c0fbd3d8c28
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6ddf65ed2a17dae2d86b0dc4582f1d3158328898
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="errorreport-report-internal-linker-errors"></a>/ERRORREPORT (Weiterleiten von internen Linkerfehlern)

> **/ errorreport:**[ **keine** | **Eingabeaufforderung** | **Warteschlange** | **senden** ]

## <a name="arguments"></a>Argumente

**none**  
Berichte zu internen Compilerfehlern werden nicht gesammelt oder an Microsoft gesendet.

**Aufforderung**  
Sie werden aufgefordert, einen Bericht zu senden, wenn Sie einen internen Compilerfehler empfangen. **Eingabeaufforderung** ist die Standardeinstellung, wenn eine Anwendung in der Entwicklungsumgebung kompiliert wird.

**Warteschlange**  
Der Fehlerbericht wird in die Warteschlange gesetzt. Wenn Sie sich mit Administratorrechten anmelden, wird ein Fenster angezeigt, sodass Sie alle Fehler seit der letzten Ausführung melden können, wurden Sie sich angemeldet (nicht werden Sie aufgefordert, Fehlerberichte Senden von mehr als einmal alle drei Tage). **Warteschlange** ist die Standardeinstellung, wenn eine Anwendung in einer Befehlszeile kompiliert wird.

**Senden**  
Automatisch Berichte über interne Compilerfehler an Microsoft gesendet, sofern reporting durch die Einstellungen für Windows-Fehlerberichterstattung aktiviert ist.

## <a name="remarks"></a>Hinweise

Die **/errorreport** Option können Sie die Informationen interner Compilerfehler (ICE) direkt an Microsoft zu senden.

Die Option **/errorreport: Send** automatisch Fehlerinformationen an Microsoft sendet, wenn von Windows Error Reporting Service-Einstellungen aktiviert.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Öffnen der **Konfigurationseigenschaften** > **Linker** > **erweitert** Eigenschaftenseite.

1. Ändern der **-Fehlerberichterstattung** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ErrorReporting%2A>.

## <a name="see-also"></a>Siehe auch

[/ errorreport (Bericht interne Compilerfehler)](../../build/reference/errorreport-report-internal-compiler-errors.md)  
[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)  
[Linkeroptionen](../../build/reference/linker-options.md)  
