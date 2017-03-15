---
title: "TN071: MFC-IOleCommandTarget-Implementierung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IOleCommandTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IOleCommandTarget-Schnittstelle"
  - "TN071"
ms.assetid: 3eef571e-6357-444d-adbb-6f734a0c3161
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# TN071: MFC-IOleCommandTarget-Implementierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert.  Daher können einige Verfahren und Themen veraltet oder falsch sein.  Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Die `IOleCommandTarget`\-Schnittstelle können Objekte und deren Container auf Dispatch Befehle miteinander.  Beispielsweise enthalten die Symbolleisten eines Objekts Schaltflächen für Befehle wie **Drucken**, **Seitenansicht**, **Speichern**, **Zoom** und `New`.  Wird ein solches Objekt in einem Container eingebettet wurden, der `IOleCommandTarget` unterstützt, kann das Objekt die Schaltflächen aktivieren und leiten die Befehle am Container zur Verarbeitung, wenn der Benutzer auf sie geklickt hat.  Wenn ein Container das eingebettete Objekt sich drucken bat, kann er diese Anforderung stellen, indem ein Befehl durch die `IOleCommandTarget`\-Schnittstelle des eingebetteten Objekts gesendet.  
  
 `IOleCommandTarget` ist eine Automatisierung ähnliche Schnittstelle darin, dass sie von einem Client verwendet wird, um Methoden aufzurufen. auf einem Server  jedoch mit `IOleCommandTarget` speichert den Mehraufwand gehindert Aufrufe über Automatisierungsschnittstellen, da Programmierer die normalerweise kostenintensive `Invoke`\-Methode aus `IDispatch` nicht verwenden müssen.  
  
 In MFC wird die `IOleCommandTarget`\-Schnittstelle durch Active Document\-Server verwendet, um Active Document\-Container zu den Dispatchbefehlen zum Server zu ermöglichen.  Die Active Document\-Server\-Klasse, `CDocObjectServerItem`, Schnittstellenzuordnungen der die MFC \(siehe [TN038: Implementierung MFC\/OLE IUnknown](../mfc/tn038-mfc-ole-iunknown-implementation.md)\), um die `IOleCommandTarget`\-Schnittstelle implementieren.  
  
 `IOleCommandTarget` wird auch in der **COleFrameHook**\-Klasse implementiert.  **COleFrameHook** ist eine nicht dokumentierten MFC\-Klasse, die die Rahmenfensterfunktionalität von Containern der direkten Bearbeitung implementiert.  **COleFrameHook** verwendet auch MFC\-Schnittstellenzuordnungen, die die `IOleCommandTarget`\-Schnittstelle implementieren.  **COleFrameHook** Implementierung von `IOleCommandTarget` leitet OLE\-Befehle an `COleDocObjectItem` abgeleitete Active Document\-Container weiter.  Dies ermöglicht es jedem MFC\-ActiveDocument\-Container, um Meldungen von enthaltenden Active Document\-Servern zu empfangen.  
  
## Befehls\-Zuordnungen MFC\-OLE  
 MFC\-Entwickler können `IOleCommandTarget` verwenden, indem Befehlszuordnungen MFC\-OLE verwenden.  OLE\-Befehlszuordnungen sind z Meldungszuordnungen, da sie verwendet werden können, um zu OLE\-Befehlen Memberfunktionen der Klasse zugeordnet, die die Befehlszuordnung enthält.  Um diese Arbeit, Platzmakros in der Befehlszuordnung der OLE\-Befehlsgruppe des Befehls angeben werden, den Sie verarbeiten möchten, den OLE\-Befehl und die Befehls\-ID von [Da WM\_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) der Meldung, die übermittelt wird, wenn der OLE\-Befehl empfangen wird.  MFC stellt auch einige vordefinierte Makros für Standard\-OLE\-Befehle bereit.  Eine Liste der Befehle standardmäßigen OLE, die ursprünglich für Microsoft Office\-Anwendungen entworfen wurden, finden Sie die OLECMDID\-Enumeration, die in docobj.h definiert wird.  
  
 Wenn ein OLE\-Befehl von einer MFC\-Anwendung empfangen wird, die eine OLE\-Befehlszuordnung enthält, versucht MFC, die Befehls\-ID und die angeforderten Befehlsgruppe für den Befehl in der OLE\-Befehlszuordnung der Anwendung zu suchen.  Wenn eine Übereinstimmung gefunden wird, wird eine **WM\_COMMAND** Meldung an die Anwendung gesendet, die die Befehlszuordnung mit der ID des angeforderten Befehls enthält. \(Siehe die Beschreibung von `ON_OLECMD` weiter unten.\) Auf diese Weise werden OLE\-Befehle, die einer Anwendung weitergeleitet werden, an **WM\_COMMAND** Meldungen von MFC ausgeführt.  Die **WM\_COMMAND** Meldungen werden dann durch die Meldungszuordnungen der Anwendung mithilfe der standardmäßigen [Befehlsrouting](../mfc/command-routing.md) Architektur MFC weitergeleitet.  
  
 Im Gegensatz Meldungszuordnungen werden Befehlszuordnungen MFC\-OLE nicht durch die unterstützt.  MFC\-Entwickler müssen OLE\-Befehlszuordnungsstütz\- und OLE\-Befehlszuordnungseinträge von Hand hinzufügen.  OLE\-Befehlszuordnungen können zu MFC\-ActiveDocument\-Servern einer beliebigen Klasse hinzugefügt werden, die in der **WM\_COMMAND** MeldungRoutingkette ist, zum Zeitpunkt, welches das aktive Dokument in einem Container direkt aktiv ist.  Diese Klassen umfassen die Klassen der Anwendung, die von [CWinApp](../mfc/reference/cwinapp-class.md), [CView](../mfc/reference/cview-class.md), [CDocument](../mfc/reference/cdocument-class.md) und [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md) abgeleitet sind.  In den Active Document\-Container können OLE\-Befehlszuordnungen zu [COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md) nur hinzugefügt werden abgeleiteten Klasse.  Auch in den Active Document\-Container, werden die Funktionen **WM\_COMMAND** Meldungen nur zur Meldungszuordnung in `COleDocObjectItem` abgeleitete Klasse weitergeleitet.  
  
## OLE Zuordnungs\-Makros dominiert  
 Verwenden Sie die folgenden Makros, um Befehlszuordnungsfunktionalität der Klasse hinzufügen:  
  
```  
  
DECLARE_OLECMD_MAP ()  
  
```  
  
 Dieses Makro wird in der Klassendeklaration \(in der Regel in der Headerdatei\) der Klasse, die die Befehlszuordnung enthält.  
  
```  
  
BEGIN_OLECMD_MAP(  
theClass  
,   
baseClass  
)  
  
```  
  
 `theClass`  
 Name der Klasse, die die Befehlszuordnung enthält.  
  
 `baseClass`  
 Name der Basisklasse der Klasse, die die Befehlszuordnung enthält.  
  
 Dieses Makro markiert den Anfang der Befehlszuordnung.  Verwenden Sie dieses Makro in der Implementierungsdatei für die Klasse, die die Befehlszuordnung enthält.  
  
```  
  
END_OLECMD_MAP()  
  
```  
  
 Dieses Makro markiert das Ende der Befehlszuordnung.  Verwenden Sie dieses Makro in der Implementierungsdatei für die Klasse, die die Befehlszuordnung enthält.  Dieses Makro muss das **BEGIN\_OLECMD\_MAP**\-Makro immer erfolgreich sind.  
  
```  
  
ON_OLECMD(  
pguid  
,   
olecmdid  
,   
id  
)  
  
```  
  
 `pguid`  
 Zeiger der GUID der OLE\-Befehlsgruppe des Befehls.  Dieser Parameter ist **NULL** für die Befehlsgruppe standardmäßigen OLE.  
  
 *olecmdid*  
 OLE\-Befehls\-ID des Befehls aufgerufen werden.  
  
 `id`  
 ID der zur Anwendung gesendet werden **WM\_COMMAND**, Meldung, die die Befehlszuordnung enthält, wenn dieser OLE\-Befehl aufgerufen wird.  
  
 Verwenden Sie das `ON_OLECMD`\-Makro in der Befehlszuordnung, um Einträge für die OLE\-Befehle hinzuzufügen, die Sie behandeln möchten.  Wenn die OLE\-Befehle empfangen werden, werden diese der Meldung angegebenen **WM\_COMMAND** konvertiert und weitergeleitet durch die Meldungszuordnung der Anwendung mithilfe der BefehlRoutingarchitektur standardmäßigen MFC.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie OLE\-BefehlBehandlungsfunktion einem MFC\-ActiveDocument\-Server hinzufügt, den Befehl [OLECMDID\_PRINT](http://msdn.microsoft.com/library/windows/desktop/ms691264) OLE zu behandeln.  Dieses Beispiel übernimmt dessen Sie verwendeter Anwendungs\-Assistent an, eine MFC\-Anwendung zu generieren, die ein Active Document\-Server ist.  
  
1.  In Ihrem `CView`\- die Headerdatei der abgeleiteten Klasse, fügen den `DECLARE_OLECMD_MAP`\-Makro der Klassendeklaration hinzu.  
  
    > [!NOTE]
    >  Verwenden Sie `CView` abgeleitete Klasse, da eine der Klassen im Active Document\-Server ist, der in der **WM\_COMMAND** MeldungRoutingkette ist.  
  
    ```  
    class CMyServerView : public CView  
    {  
    protected: // create from serialization only  
       CMyServerView();  
       DECLARE_DYNCREATE(CMyServerView)  
       DECLARE_OLECMD_MAP()  
    . . .  
    };  
    ```  
  
2.  In der Implementierungsdatei für von `CView` abgeleitete Klasse, fügen die Makros `BEGIN_OLECMD_MAP` und `END_OLECMD_MAP` hinzu:  
  
    ```  
    BEGIN_OLECMD_MAP(CMyServerView, CView)  
  
    END_OLECMD_MAP()  
    ```  
  
3.  Um den Druckbefehl standardmäßigen OLE zu behandeln, fügen Sie einem Makro [ON\_OLECMD](../Topic/ON_OLECMD.md) der Befehlszuordnung hinzu, die der OLE\-Befehls\-ID für den Standarddruckbefehl und **ID\_FILE\_PRINT** für die **WM\_COMMAND** ID angibt  **ID\_FILE\_PRINT** ist die Standarddruckbefehls\-id, die von Anwendungs\-Assistent\-generierte MFC\-Anwendungen verwendet wird:  
  
    ```  
    BEGIN_OLECMD_MAP(CMyServerView, CView)  
       ON_OLECMD(NULL,OLECMDID_PRINT,ID_FILE_PRINT)  
    END_OLECMD_MAP()  
    ```  
  
 Beachten Sie dies der Befehlsmakros standardmäßigen OLE, die in afxdocob.h, kann anstelle des Makros `ON_OLECMD` verwendet werden, da **OLECMDID\_PRINT** eine ID Befehl standardmäßigen OLE ist  Das `ON_OLECMD_PRINT`\-Makro wird die gleiche Aufgabe wie das `ON_OLECMD`\-Makro, das oben angezeigt wird.  
  
 Wenn eine Containeranwendung diesen Server ein **OLECMDID\_PRINT** Befehl durch die `IOleCommandTarget`\-Schnittstelle des Servers sendet, wird der MFC\-Druckbefehlshandler im Server aufgerufen und der Server, die Anwendung zu drucken.  Der Code des Active Document\-Container, um den Druckbefehls aufzurufen, der in den oben genannten Schritte hinzugefügt wurde, würde etwa folgendermaßen aussehen:  
  
```  
void CContainerCntrItem::DoOleCmd()  
{  
   IOleCommandTarget *pCmd = NULL;  
   HRESULT hr = E_FAIL;  
   OLECMD ocm={OLECMDID_PRINT, 0};  
  
   hr = m_lpObject->QueryInterface(IID_IOleCommandTarget,reinterpret_cast<void**>(&pCmd));  
   if(FAILED(hr))  
      return;  
  
   hr = pCmd->QueryStatus(NULL, 1, &ocm, NULL);  
   if(SUCCEEDED(hr) && (ocm.cmdf & OLECMDF_ENABLED))  
   {  
      //Command is available and enabled so call it  
      COleVariant vIn;  
      COleVariant vOut;  
      hr = pCmd->Exec(NULL, OLECMDID_PRINT,  
 OLECMDEXECOPT_DODEFAULT, &vIn, &vOut);  
      ASSERT(SUCCEEDED(hr));  
   }  
   pCmd->Release();  
}  
```  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)