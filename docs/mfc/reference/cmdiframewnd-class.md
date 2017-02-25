---
title: "CMDIFrameWnd Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMDIFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMDIFrameWnd class"
  - "MDI frame windows"
ms.assetid: fa8736e6-511b-4c51-8b4d-eba78378aeb9
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMDIFrameWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Rahmenfensterfunktionen Windows\-MultipleDocument Interface\), zusammen mit Member zum Verwalten des Fensters.  
  
## Syntax  
  
```  
class CMDIFrameWnd : public CFrameWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMDIFrameWnd::CMDIFrameWnd](../Topic/CMDIFrameWnd::CMDIFrameWnd.md)|Erstellt einen `CMDIFrameWnd`.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMDIFrameWnd::CreateClient](../Topic/CMDIFrameWnd::CreateClient.md)|Stellt ein Fenster Windows **MDICLIENT** für dieses `CMDIFrameWnd` erstellt.  Aufgerufen durch die `OnCreate`\-Memberfunktion der `CWnd`.|  
|[CMDIFrameWnd::CreateNewChild](../Topic/CMDIFrameWnd::CreateNewChild.md)|Stellt ein neues untergeordnetes Fenster erstellt.|  
|[CMDIFrameWnd::GetWindowMenuPopup](../Topic/CMDIFrameWnd::GetWindowMenuPopup.md)|Gibt das Fensterpopupmenü zurück.|  
|[CMDIFrameWnd::MDIActivate](../Topic/CMDIFrameWnd::MDIActivate.md)|Aktiviert ein weiteres untergeordnetes MDI\-Fenster.|  
|[CMDIFrameWnd::MDICascade](../Topic/CMDIFrameWnd::MDICascade.md)|Ordnet alle untergeordneten überlappende Fenster in einem Format an.|  
|[CMDIFrameWnd::MDIGetActive](../Topic/CMDIFrameWnd::MDIGetActive.md)|Ruft das aktuell aktive untergeordnete MDI\-Fenster ab, zusammen mit einem Flag angibt, ob das untergeordnete Element maximiert wird.|  
|[CMDIFrameWnd::MDIIconArrange](../Topic/CMDIFrameWnd::MDIIconArrange.md)|Ordnet alle minimierten Dokumentenuntergeordneten Vorschaufenster an.|  
|[CMDIFrameWnd::MDIMaximize](../Topic/CMDIFrameWnd::MDIMaximize.md)|Maximiert untergeordnetes MDI\-Fenster.|  
|[CMDIFrameWnd::MDINext](../Topic/CMDIFrameWnd::MDINext.md)|Ermöglicht das untergeordnete Fenster unmittelbar hinter dem derzeit aktiven untergeordneten Fenster und platziert momentan aktiven untergeordneten Fenster hinter allen anderen untergeordneten Fenstern.|  
|[CMDIFrameWnd::MDIPrev](../Topic/CMDIFrameWnd::MDIPrev.md)|Ermöglicht das vorherige untergeordnete Fenster und gibt das aktuell aktive untergeordnete Fenster unmittelbar hinter es.|  
|[CMDIFrameWnd::MDIRestore](../Topic/CMDIFrameWnd::MDIRestore.md)|Stellt ein untergeordnetes MDI\-Fenster von erhöht oder minimiertem Größe zurückgesetzt.|  
|[CMDIFrameWnd::MDISetMenu](../Topic/CMDIFrameWnd::MDISetMenu.md)|Ersetzt das Menü eines MDI\-Rahmenfensters, des Fensterpopupmenüs oder der beider.|  
|[CMDIFrameWnd::MDITile](../Topic/CMDIFrameWnd::MDITile.md)|Ordnet alle untergeordneten Fenster in einem gekachelten Format an.|  
  
## Hinweise  
 Um ein nützliches MDI\-Rahmenfenster für die Anwendung zu erstellen, leiten Sie eine Klasse von `CMDIFrameWnd`.  Fügen Sie Membervariablen der abgeleiteten Klasse Speicherdatenbesonderen der Anwendung hinzu.  Implementieren Sie Meldungshandlermemberfunktionen und eine Meldungszuordnung in der abgeleiteten Klasse, um anzugeben, was geschieht, wenn Meldungen in das Fenster verwiesen werden.  
  
 Sie können ein MDI\-Rahmenfenster erstellen, indem Sie die [Erstellen Sie](../Topic/CFrameWnd::Create.md) oder [LoadFrame](../Topic/CFrameWnd::LoadFrame.md)\-Memberfunktion der `CFrameWnd` aufrufen.  
  
 Bevor Sie **Create** oder `LoadFrame` aufrufen, müssen Sie das Rahmenfensterobjekt auf dem Heap mithilfe des Operators C\+\+ **new** erstellen.  Bevor kann das Aufrufen von **Create** Sie eine Fensterklasse mit der globalen Funktion [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) auch registrieren, um die Symbol\- und Klassenformate für den Frame festzulegen.  
  
 Verwenden Sie die **Create**\-Memberfunktion, um die Erstellungsparameter der Rahmen als unmittelbare Argumente zu übergeben.  
  
 `LoadFrame` erfordert weniger Argumente als **Create** und ruft stattdessen den Großteil der Standardwerte von Ressourcen, einschließlich der Frame die Beschriftung, das Symbol, die Zugriffstastentabelle und das Menü ab.  Damit von `LoadFrame` zugegriffen werden, müssen für alle diese Ressourcen dieselbe Ressourcen\-ID \(beispielsweise, **IDR\_MAINFRAME**\).  
  
 Obwohl **MDIFrameWnd** von `CFrameWnd` abgeleitet ist, berechnete eine Rahmenfensterklasse von `CMDIFrameWnd` muss, nicht mit `DECLARE_DYNCREATE` deklariert werden.  
  
 Die Klasse erbt `CMDIFrameWnd` viel der Standardimplementierung von `CFrameWnd`.  Eine ausführliche Liste dieser Funktionen, verweisen Sie auf die [CFrameWnd](../../mfc/reference/cframewnd-class.md)\-Klassenbeschreibung an.  Die `CMDIFrameWnd`\-Klasse verfügt über die folgenden zusätzlichen Funktionen:  
  
-   Ein MDI\-Rahmenfenster verwaltet das **MDICLIENT** Fenster und weist dieses in Verbindung mit Steuerleisten neu an.  Das MDI\-Clientfenster ist das übergeordnete Element direkt von untergeordneten MDI\-Rahmenfenstern.  Die **WS\_HSCROLL** und **WS\_VSCROLL** Fensterstile, die auf `CMDIFrameWnd` angegeben werden, gelten für das MDI\-Clientfenster anstatt das Hauptrahmenfenster zu, sodass der Benutzer den MDI\-Clientbereich Scrollen \(wie im Windows\-Programm\-Manager\).  
  
-   Ein MDI\-Rahmenfenster besitzt ein Standard Menü, das als die Menüleiste verwendet wird, wenn kein aktives untergeordnetes MDI\-Fenster gibt.  Wenn es ein aktiven untergeordneten MDI\-Fenster gibt, wird die Menüleiste des MDI\-Rahmenfensters automatisch das Menü des untergeordneten MDI\-Fensters ersetzt.  
  
-   Ein MDI\-Rahmenfenster funktioniert in Verbindung mit dem aktuellen untergeordneten MDI\-Fenster, wenn ein aktives gibt.  Beispielsweise werden Befehlsmeldungen dem aktuell aktiven untergeordneten MDI\-Fenster vor dem MDI\-Rahmenfenster delegiert.  
  
-   Ein MDI\-Rahmenfenster hat Standardhandler für die folgenden Standardfenstermenübefehle:  
  
    -   **ID\_WINDOW\_TILE\_VERT**  
  
    -   **ID\_WINDOW\_TILE\_HORZ**  
  
    -   **ID\_WINDOW\_CASCADE**  
  
    -   **ID\_WINDOW\_ARRANGE**  
  
-   Ein MDI\-Rahmenfenster verfügt auch über eine Implementierung von **ID\_WINDOW\_NEW**, die neuer Rahmen und eine Ansicht für das aktuelle Dokument erstellt.  Eine Anwendung kann diese Standardeinstellung Befehlsimplementierungen überschreiben, um MDI\-Fensterbehandlung anzupassen.  
  
 Verwenden Sie den Operator C\+\+ **delete**, um ein Rahmenfenster zu zerstören.  Verwenden Sie stattdessen `CWnd::DestroyWindow`.  Die `CFrameWnd` Implementierung von `PostNcDestroy` löscht das C\+\+\-Objekt, wenn das Fenster zerstört wird.  Wenn der Benutzer das Rahmenfenster enthält, wird der Standardwert `OnClose`\-Handler `DestroyWindow` auf.  
  
 Weitere Informationen zu `CMDIFrameWnd`, finden Sie unter [Rahmenfenster](../../mfc/frame-windows.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIFrameWnd`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [MFC Sampling MDI](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel MDIDOCVW](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel SNAPVW](../../top/visual-cpp-samples.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [CMDIChildWnd Class](../../mfc/reference/cmdichildwnd-class.md)