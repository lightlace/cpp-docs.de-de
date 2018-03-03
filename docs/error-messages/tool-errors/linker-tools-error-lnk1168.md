---
title: Linkertoolfehler Lnk1168 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1168
dev_langs:
- C++
helpviewer_keywords:
- LNK1168
ms.assetid: 97ead151-fd99-46fe-9a1d-7e84dc0b8cc8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 12dfce4243f0872735158df7ccd81b7c6e29efc8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1168"></a>Linkertoolfehler LNK1168
'Dateiname' kann nicht zum Schreiben geöffnet werden  
  
 Der Linker kann nicht in die Datei `filename` schreiben. Die Datei wird möglicherwiese verwendet und ihr Handle wird von einem anderen Prozess gesperrt oder Sie haben keine Schreibberechtigung für die Datei bzw. für das Verzeichnis oder die Netzwerkfreigabe, in der sich die Datei befindet. Dieser Fehler wird oft durch eine vorübergehende Bedingung verursacht, z. B. eine Sperre durch ein Antivirenprogramm, einen Indizierungsprozess für eine Dateisuche oder die verzögerte Freigabe einer Sperre durch das Buildsystem [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)].  
  
 Vergewissern Sie sich zur Behebung dieses Problems, dass das Handle für die Datei `filename` nicht gesperrt ist, und dass Sie über Schreibberechtigungen für die Datei verfügen. Wenn es sich um eine ausführbare Datei handelt, überprüfen Sie, ob diese nicht bereits ausgeführt wird.  
  
 Sie können Windows SysInternals-Dienstprogramme verwenden [behandeln](http://technet.microsoft.com/sysinternals/bb896655.aspx) oder [Process Explorer](http://technet.microsoft.com/sysinternals/bb896653) um festzustellen, welcher Prozess eine Sperre auf behandeln Datei wurde `filename`. Sie können den Prozess-Explorer auch verwenden, um Sperren auf Handles von offenen Dateien aufzuheben. Weitere Informationen über die Verwendung der Hilfsprogramme finden Sie in den entsprechenden Hilfedateien zu den Programmen.  
  
 Wenn die Datei von einem Antivirenprogramm gesperrt wird, können Sie dieses Problem beheben, indem Sie die Buildausgabeverzeichnisse vom automatischen Scannen durch das Antivirenprogramm ausschließen. Virenscanner werden häufig bei der Erstellung neuer Dateien im Dateisystem ausgelöst und sperren die entsprechenden Dateien während des Scanprozesses. Informationen dazu, wie Sie bestimmte Verzeichnisse vom Scannen ausschließen können, finden Sie in der Dokumentation zum Antivirenprogramm.  
  
 Wenn die Datei durch einen Indexdienst für Suchvorgänge gesperrt wird, können Sie dieses Problem beheben, indem Sie die Buildausgabeverzeichnisse von der automatischen Indizierung ausschließen. Weitere Informationen zum Indexdienst finden Sie in der Dokumentation. Verwenden Sie zum Ändern der Windows-Indexdienst **Indizierungsoptionen** in Windows **Systemsteuerung**. Weitere Informationen finden Sie unter [Optimieren von Windows sucht mithilfe des Index: häufig gestellte Fragen](http://windows.microsoft.com/en-us/windows/improve-windows-searches-using-index-faq#1TC=windows-7).  
  
 Wenn die ausführbare Datei nicht vom Buildprozess überschrieben werden kann, wird sie möglicherweise durch den Datei-Explorer gesperrt. Wenn die **Anwendungserfahrung** Dienst wurde deaktiviert, Datei-Explorer kann in eine ausführbare Datei Handle-Sperre für längere Zeit warten. Führen Sie zur Behebung dieses Problems **"Services.msc"** und öffnen Sie dann die **Eigenschaften** im Dialogfeld für die **Anwendungserfahrung** Dienst. Ändern der **Starttyp** aus **deaktiviert** auf **manuell**.  
  
## <a name="see-also"></a>Siehe auch  
 [Sie können ein "Fehler PRJ0008" oder "Schwerwiegender Fehler LNK1168"-Fehlermeldung erhalten, wenn Sie, zum Erstellen einer Projektmappe oder ein ActiveX-Projekt in Visual C++ versuchen](http://support.microsoft.com/kb/308358)