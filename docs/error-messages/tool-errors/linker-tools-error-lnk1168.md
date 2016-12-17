---
title: "Linkertoolfehler LNK1168"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1168"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1168"
ms.assetid: 97ead151-fd99-46fe-9a1d-7e84dc0b8cc8
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK1168
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Dateiname' kann nicht zum Schreiben geöffnet werden  
  
 Der Linker kann nicht in die Datei `filename` schreiben.  Die Datei wird möglicherwiese verwendet und ihr Handle wird von einem anderen Prozess gesperrt oder Sie haben keine Schreibberechtigung für die Datei bzw. für das Verzeichnis oder die Netzwerkfreigabe, in der sich die Datei befindet.  Dieser Fehler wird oft durch eine vorübergehende Bedingung verursacht, z. B. eine Sperre durch ein Antivirenprogramm, einen Indizierungsprozess für eine Dateisuche oder die verzögerte Freigabe einer Sperre durch das Buildsystem [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)].  
  
 Vergewissern Sie sich zur Behebung dieses Problems, dass das Handle für die Datei `filename` nicht gesperrt ist, und dass Sie über Schreibberechtigungen für die Datei verfügen.  Wenn es sich um eine ausführbare Datei handelt, überprüfen Sie, ob diese nicht bereits ausgeführt wird.  
  
 Mit dem [Handle](http://technet.microsoft.com/sysinternals/bb896655.aspx) für Windows SysInternals\-Dienstprogramme oder dem [Process Explorer](http://technet.microsoft.com/sysinternals/bb896653) können Sie ermitteln, welcher Prozess eine Dateihandlesperre auf `filename` hat.  Sie können den Prozess\-Explorer auch verwenden, um Sperren auf Handles von offenen Dateien aufzuheben.  Weitere Informationen über die Verwendung der Hilfsprogramme finden Sie in den entsprechenden Hilfedateien zu den Programmen.  
  
 Wenn die Datei von einem Antivirenprogramm gesperrt wird, können Sie dieses Problem beheben, indem Sie die Buildausgabeverzeichnisse vom automatischen Scannen durch das Antivirenprogramm ausschließen.  Virenscanner werden häufig bei der Erstellung neuer Dateien im Dateisystem ausgelöst und sperren die entsprechenden Dateien während des Scanprozesses.  Informationen dazu, wie Sie bestimmte Verzeichnisse vom Scannen ausschließen können, finden Sie in der Dokumentation zum Antivirenprogramm.  
  
 Wenn die Datei durch einen Indexdienst für Suchvorgänge gesperrt wird, können Sie dieses Problem beheben, indem Sie die Buildausgabeverzeichnisse von der automatischen Indizierung ausschließen.  Weitere Informationen zum Indexdienst finden Sie in der Dokumentation.  Wenn Sie den Windows\-Indexdienst für Suchvorgänge ändern möchten, verwenden Sie in der Windows\-**Systemsteuerung** die Option **Indizierungsoptionen**.  Weitere Informationen finden Sie unter [Optimieren von Windows\-Suchvorgängen mithilfe des Index: Häufig gestellte Fragen](http://windows.microsoft.com/de-de/windows/improve-windows-searches-using-index-faq#1TC=windows-7).  
  
 Wenn die ausführbare Datei nicht vom Buildprozess überschrieben werden kann, wird sie möglicherweise durch den Datei\-Explorer gesperrt.  Wenn der Dienst **Anwendungserfahrung** deaktiviert wurde, hat der Datei\-Explorer das Handle der ausführbaren Datei möglicherweise für längere Zeit mit einer Sperre versehen.  Führen Sie zur Behebung dieses Problems **services.msc** aus und öffnen Sie anschließend das Dialogfeld **Eigenschaften** für den Dienst **Anwendungserfahrung**.  Ändern Sie den **Starttyp** von **Deaktiviert** in **Manuell**.  
  
## Siehe auch  
 [Sie werden möglicherweise die Meldung "Fehler PRJ0008" oder "Schwerwiegender Fehler LNK1168" erhalten, wenn Sie versuchen, eine Projektmappe oder ein ActiveX\-Projekt in Visual C\+\+ zu erstellen](http://support.microsoft.com/kb/308358)