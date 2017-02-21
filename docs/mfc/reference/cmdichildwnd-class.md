---
title: "CMDIChildWnd Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMDIChildWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Untergeordnete Fenster, CMDIChildWnd class"
  - "CMDIChildWnd class"
  - "MDI [C++], Untergeordnete Fenster"
  - "windows [C++], MDI"
ms.assetid: 6d07f5d4-9a3e-4723-9fa5-e65bb669fdd5
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMDIChildWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität eines untergeordneten Windows\-MultipleDocument Interface \(MDI\)\-Fensters, zusammen mit Member zum Verwalten des Fensters.  
  
## Syntax  
  
```  
class CMDIChildWnd : public CFrameWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMDIChildWnd::CMDIChildWnd](../Topic/CMDIChildWnd::CMDIChildWnd.md)|Erstellt ein `CMDIChildWnd`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMDIChildWnd::Create](../Topic/CMDIChildWnd::Create.md)|Stellt das Windows\-untergeordneteMDI\-Fenster erstellt, das mit dem `CMDIChildWnd`\-Objekt zugeordnet ist.|  
|[CMDIChildWnd::GetMDIFrame](../Topic/CMDIChildWnd::GetMDIFrame.md)|Gibt den Rahmen des übergeordneten MDI\-Formular des MDI\-Clientfensters zurück.|  
|[CMDIChildWnd::MDIActivate](../Topic/CMDIChildWnd::MDIActivate.md)|Ermöglicht das untergeordnete MDI\-Fenster.|  
|[CMDIChildWnd::MDIDestroy](../Topic/CMDIChildWnd::MDIDestroy.md)|Zerstört dieses untergeordnete MDI\-Fenster.|  
|[CMDIChildWnd::MDIMaximize](../Topic/CMDIChildWnd::MDIMaximize.md)|Maximiert dieses untergeordnete MDI\-Fenster.|  
|[CMDIChildWnd::MDIRestore](../Topic/CMDIChildWnd::MDIRestore.md)|Stellt dieses untergeordnete MDI\-Fenster von erhöht oder minimiertem Größe zurückgesetzt.|  
|[CMDIChildWnd::SetHandles](../Topic/CMDIChildWnd::SetHandles.md)|Legt die Handles für Menu\- und Zugriffstastenressourcen fest.|  
  
## Hinweise  
 Ein untergeordnetes MDI\-Fenster sieht ähnlich wie ein typisches Rahmenfenster, außer dass das untergeordnete MDI\-Fenster wird innerhalb eines MDI\-Rahmenfensters statt auf dem Desktop.  Ein untergeordnetes MDI\-Fenster hat keine Menüleiste aus der eigenen, sondern stattdessen das Menü des MDI\-Rahmenfensters frei.  Das Framework ändert automatisch das MDI\-Framemenü, um das aktive untergeordnete MDI\-Fenster derzeit darzustellen.  
  
 Um ein nützliches untergeordnetes MDI\-Fenster für die Anwendung zu erstellen, leiten Sie eine Klasse von `CMDIChildWnd`.  Fügen Sie Membervariablen der abgeleiteten Klasse Speicherdatenbesonderen der Anwendung hinzu.  Implementieren Sie Meldungshandlermemberfunktionen und eine Meldungszuordnung in der abgeleiteten Klasse, um anzugeben, was geschieht, wenn Meldungen in das Fenster verwiesen werden.  
  
 Es gibt drei Möglichkeiten, untergeordnetes MDI\-Fenster zu erstellen:  
  
-   Erstellen Sie es direkt mithilfe **Create**.  
  
-   Erstellen Sie es direkt mithilfe `LoadFrame`.  
  
-   Erstellen Sie es indirekt über eine Normal\-Vorlage.  
  
 Bevor Sie **Create** oder `LoadFrame` aufrufen, müssen Sie das Rahmenfensterobjekt auf dem Heap mithilfe des Operators C\+\+ **new** erstellen.  Bevor kann das Aufrufen von **Create** Sie eine Fensterklasse mit der globalen Funktion [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) auch registrieren, um die Symbol\- und Klassenformate für den Frame festzulegen.  
  
 Verwenden Sie die **Create**\-Memberfunktion, um die Erstellungsparameter der Rahmen als unmittelbare Argumente zu übergeben.  
  
 `LoadFrame` erfordert weniger Argumente als **Create** und ruft stattdessen den Großteil der Standardwerte von Ressourcen, einschließlich der Frame die Beschriftung, das Symbol, die Zugriffstastentabelle und das Menü ab.  Um nach `LoadFrame` möglich ist, müssen alle diese Ressourcen dieselbe Ressourcen\-ID \(beispielsweise, **IDR\_MAINFRAME**\) verfügen.  
  
 Wenn ein Objekt `CMDIChildWnd` Ansichten und Dokumente enthält, werden sie indirekt durch das Framework statt direkt von des Programmierers erstellt.  Das Objekt `CDocTemplate` instrumentiert die Erstellung von Rahmen, die Erstellung der enthaltenen Ansichten und die Verbindung der Ansichten zum entsprechenden Dokument.  Die Parameter des `CDocTemplate`\-Konstruktors geben `CRuntimeClass`, der drei betroffenen Klassen an \(Dokument, Frames und Ansicht\).  Ein Objekt `CRuntimeClass` wird durch das Framework verwendet, um neue Frames dynamisch zu erstellen, wenn es vom Benutzer angegeben wird \(beispielsweise, mithilfe des Befehls der neuen Datei oder eines neuen Befehls MDI\-Fensters\).  
  
 Eine Rahmenfensterklasse, die von `CMDIChildWnd` abgeleitet ist, muss deklariert werden mit `DECLARE_DYNCREATE`, damit der obige `RUNTIME_CLASS` Mechanismus ordnungsgemäß funktioniert.  
  
 Die Klasse erbt `CMDIChildWnd` viel der Standardimplementierung von `CFrameWnd`.  Eine ausführliche Liste dieser Funktionen, verweisen Sie die [CFrameWnd](../../mfc/reference/cframewnd-class.md)\-Klassenbeschreibung an.  Die `CMDIChildWnd`\-Klasse verfügt über die folgenden zusätzlichen Funktionen:  
  
-   In Verbindung mit der `CMultiDocTemplate`\-Klasse geben mehrere `CMDIChildWnd`\-Objekte aus der gleichen Normal\-Vorlage dasselbe Menü frei und speichern Windows\-Systemressourcen.  
  
-   Das aktuell aktive Menü des untergeordneten MDI\-Fensters ersetzt vollständig das Menü MDI\-Rahmenfensters und die Beschriftung der aktuell aktiven untergeordneten MDI\-Fenster wird der Beschriftung des MDI\-Rahmenfensters hinzugefügt.  Weitere Beispiele für Funktionen des untergeordneten MDI\-Fensters, die in Verbindung mit einem MDI\-Rahmenfenster implementiert werden, finden Sie unter `CMDIFrameWnd`\-Klassenbeschreibung.  
  
 Verwenden Sie den Operator C\+\+ **delete**, um ein Rahmenfenster zu zerstören.  Verwenden Sie stattdessen `CWnd::DestroyWindow`.  Die `CFrameWnd` Implementierung von `PostNcDestroy` löscht das C\+\+\-Objekt, wenn das Fenster zerstört wird.  Wenn der Benutzer das Rahmenfenster enthält, wird der Standardwert `OnClose`\-Handler `DestroyWindow` auf.  
  
 Weitere Informationen zu `CMDIChildWnd`, finden Sie unter [Rahmenfenster](../../mfc/frame-windows.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIChildWnd`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [MFC Sampling MDI](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel MDIDOCVW](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel SNAPVW](../../top/visual-cpp-samples.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd Class](../../mfc/reference/cmdiframewnd-class.md)