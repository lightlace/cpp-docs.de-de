---
title: 'TN041: MFC-OLE1-Migration zu MFC-OLE 2 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE1 [MFC]
- migrating OLE1 to OLE2
- migration [MFC], OLE1 to OLE2
- OLE2 [MFC]
- porting OLE1 to OLE2
- converting OLE1 to OLE2
- upgrading Visual C++ applications [MFC], OLE1 to OLE2
- TN041
ms.assetid: 67f55552-4b04-4ddf-af0b-4d9eaf5da957
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 78faa19263ff0ea03aac891c9be3a6114f7f9a48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385403"
---
# <a name="tn041-mfcole1-migration-to-mfcole-2"></a>TN041: MFC/OLE1-Migration zu MFC/OLE 2
> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
## <a name="general-issues-relating-to-migration"></a>Allgemeine Probleme im Zusammenhang mit der Migration  
 Eines der Ziele beim Entwurf für die OLE-2-Klassen in MFC 2.5 (und höher) wurde ein Großteil der Architektur sollten antwortplan in MFC 2.0 für die Unterstützung für OLE-1.0 beibehalten werden sollen. Daher viele der gleichen OLE-Klassen in MFC 2.0 noch vorhanden sind in dieser Version von MFC (`COleDocument`, `COleServerDoc`, `COleClientItem`, `COleServerItem`). Darüber hinaus sind viele der APIs in diesen Klassen genau identisch. OLE 2 ist jedoch OLE 1.0 erheblich unterscheiden, damit Sie erwarten können, dass einige Details geändert wurden. Wenn Sie mit Unterstützung für MFC-2.0 OLE1 vertraut sind, müssen Sie zu Hause mit MFC 2.0-Unterstützung können.  
  
 Wenn Sie eine vorhandene MFC/OLE1-Anwendung erstellen und OLE-2-Funktionen hinzugefügt, sollten Sie zunächst diesen Hinweis lesen. In diesem Hinweis werden einige allgemeine Probleme beim Portieren von MFC/OLE 2 die Funktionalität OLE1 auftreten und dann wird erläutert, die Probleme beim Portieren von zwei Anwendungen, die in MFC 2.0 enthaltenen aufgedeckt behandelt: MFC-OLE-Beispielen [OCLIENT](../visual-cpp-samples.md) und [HIERSVR](../visual-cpp-samples.md).  
  
## <a name="mfc-documentview-architecture-is-important"></a>MFC-Dokument-/ Ansichtarchitektur ist wichtig  
 Wenn Ihre Anwendung keine MFC Dokument-/ Ansichtarchitektur verwendet und OLE-2-Unterstützung für Ihre Anwendung hinzufügen möchten, ist nun die Zeit auf Dokument-/Ansichtarchitektur verschieben. Viele der Vorteile von MFC OLE-2-Klassen werden nur realisiert, sobald Ihre Anwendung die integrierte Architektur und die Komponenten von MFC verwendet wird.  
  
 Implementieren einen Server oder den Container ohne Verwendung der MFC-Architektur ist möglich, aber nicht empfehlenswert.  
  
## <a name="use-mfc-implementation-instead-of-your-own"></a>Verwenden Sie MFC-Implementierung, anstatt eine eigene  
 Klassen wie MFC "vorprogrammierten Implementierung" `CToolBar`, `CStatusBar`, und `CScrollView` haben integrierte Groß-/Kleinschreibung spezialcode für OLE-2-Unterstützung. Bei Verwendung dieser Klassen in der Anwendung müssen Sie daher von den Endbenutzern diese abgelegt zu OLE bewusst machen profitieren. Erneut, es ist möglich, hier "Roll-your-own" Klassen für diese Zwecke, aber es wird nicht empfohlen. Wenn Sie eine ähnliche Funktionalität implementieren müssen, ist die MFC-Quellcode eine ausgezeichnete Verweis für den Umgang mit einigen feiner Punkte des OLE (insbesondere, wenn es darum geht, direkte Aktivierung).  
  
## <a name="examine-the-mfc-sample-code"></a>Überprüfen Sie den Code der MFC-Beispiel  
 Es gibt eine Anzahl von MFC-Beispiele, die OLE-Funktionen enthalten. Jede dieser Anwendungen implementiert OLE aus einem anderen Winkel aus:  
  
- [HIERSVR](../visual-cpp-samples.md) hauptsächlich zur Verwendung als eine Serveranwendung gedacht. Es wurde wurde in MFC 2.0 als Anwendung MFC/OLE1 eingeschlossen und zu MFC/OLE 2 portiert und dann erweitert, dass es viele OLE-Funktionen in OLE 2 implementiert.  
  
- [OCLIENT](../visual-cpp-samples.md) Dies ist eine eigenständige containeranwendung vorgesehen, die viele der OLE-Funktionen aus Sicht der Container zu veranschaulichen. Es zu portiert wurde von MFC 2.0, und klicken Sie dann erweitert, um viele erweiterten OLE-Funktionen, z. B. benutzerdefinierte Zwischenablageformate und Links zu eingebetteten Elementen unterstützt.  
  
- [DRAWCLI](../visual-cpp-samples.md) dieser Anwendung implementiert OLE-Container-Unterstützung ähnlich wie OCLIENT der Fall ist, mit dem Unterschied, dass dies der Fall im Rahmen einer vorhandenen objektorientierte Zeichenprogramm ist. Hier erfahren Sie, wie Sie OLE-Container-Unterstützung implementieren, und in die vorhandene Anwendung integrieren können.  
  
- [SUPERPAD](../visual-cpp-samples.md) diese Anwendung als auch eine gut eigenständige Anwendung wird auch ein OLE-Server ist. Die serverunterstützung implementiert ist ziemlich minimalistischen. Von besonderem Interesse ist, wie er OLE-Zwischenablage-Dienste verwendet, um Daten in die Zwischenablage zu kopieren, aber verwendet die Funktionalität für das Steuerelement zum Windows "Bearbeiten" integriert, um Zwischenablage einfügen-Funktionalität zu implementieren. Dies zeigt eine interessante Mischung von herkömmlichen Windows-API-Nutzung sowie die Integration in die neue OLE-APIs.  
  
 Weitere Informationen zu Beispielanwendungen finden Sie unter der "MFC-Beispiel Help".  
  
## <a name="case-study-oclient-from-mfc-20"></a>Fallstudie: OCLIENT von MFC 2.0  
 Wie weiter oben erläutert [OCLIENT](../visual-cpp-samples.md) wurde in MFC 2.0 und OLE mit MFC/OLE1 implementiert. Die Schritte, mit denen diese Anwendung zunächst konvertiert wurde, um die Klassen von MFC/OLE 2 verwenden, werden nachfolgend beschrieben. Eine Reihe von Funktionen wurden hinzugefügt, nachdem der erste Port abgeschlossen wurde, um die MFC/OLE-Klassen besser zu veranschaulichen. Diese Funktionen werden hier nicht behandelt; finden Sie im Beispiel für Weitere Informationen zu diesen erweiterten Funktionen.  
  
> [!NOTE]
>  Die Compiler-Fehler und die schrittweise wurde mit Visual C++-2.0 erstellt. Bestimmte Fehlermeldungen und Speicherorte mit Visual C++ 4.0 geändert haben, jedoch bleibt gültig, die konzeptionelle Informationen.  
  
## <a name="getting-it-up-and-running"></a>Einrichten des Projekts und ausführen  
 So portieren Sie das Beispiel OCLIENT zu MFC/OLE-Ansatz ist, beginnt mit der Erstellung und beheben die offensichtliche Compilerfehler, die sich ergeben, werden. Wenn Sie MFC 2.0 OCLIENT-Beispiel dauern und kompilieren Sie ihn unter dieser Version von MFC, finden Sie, dass nicht das viele Fehler zu beheben. Die Fehler in der Reihenfolge, in der sie aufgetreten sind, werden nachfolgend beschrieben.  
  
## <a name="compile-and-fix-errors"></a>Kompilierung und Behebung von Fehlern  
  
```  
\oclient\mainview.cpp(104) : error C2660: 'Draw' : function does not take 4 parameters  
```  
  
 Der erste Fehler betrifft `COleClientItem::Draw`. In MFC/OLE1 benötigt weitere Parameter als die MFC/OLE-Version verwendet wurde. Die zusätzlichen Parameter wurden häufig nicht erforderlich und in der Regel NULL (wie in diesem Beispiel). Diese Version von MFC kann automatisch die Werte für die LpWBounds fest, wenn der CDC, die gezeichnet wird eine Metadatei DC ist. Da das Framework eine über das "Attribut DC" den übergebenen Gebietsschemaparameter pDC erstellen, ist der pFormatDC Parameter darüber hinaus nicht mehr erforderlich. Um dieses Problem zu beheben, einfach die beiden entfernt zusätzliche NULL-Parameter, um den Draw-Aufruf.  
  
```  
\oclient\mainview.cpp(273) : error C2065: 'OLE_MAXNAMESIZE' : undeclared identifier  
\oclient\mainview.cpp(273) : error C2057: expected constant expression  
\oclient\mainview.cpp(280) : error C2664: 'CreateLinkFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '  
\oclient\mainview.cpp(286) : error C2664: 'CreateFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '  
\oclient\mainview.cpp(288) : error C2664: 'CreateStaticFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '  
```  
  
 Die Fehler oben Ergebnis "naiv", die alle die **COleClientItem::CreateXXXX** Funktionen in MFC/OLE1 erforderlich, dass ein eindeutiger Name übergeben werden, um das Element darzustellen. Dies ist eine Voraussetzung für die zugrunde liegenden OLE-API. Dies ist nicht erforderlich, in MFC/OLE 2, da OLE 2 nicht DDE als zugrunde liegenden Mechanismus für die Kommunikation verwendet wird (der Name in DDE-Konversationen verwendet wurde). Um dieses Problem zu beheben, entfernen Sie die **CreateNewName** Funktion sowie alle Verweise darauf. Es ist einfach, um herauszufinden, was in dieser Version jedes MFC/OLE-Funktion erwartet wird, einfach durch Platzieren Sie den Cursor auf den Aufruf aus, und drücken F1.  
  
 Ein weiterer Bereich, der erheblich unterscheidet ist OLE 2 Zwischenablage Behandlung. Mit OLE1 verwendet haben Sie die Windows-Zwischenablage, die APIs interagieren, die per Zwischenablage. Mit OLE 2 erfolgt dies mit einem anderen Mechanismus. Die MFC/OLE1-APIs davon ausgehen, dass vor dem kopieren die Zwischenablage geöffnet war ein `COleClientItem` Objekt in die Zwischenablage. Dies ist nicht mehr erforderlich und führt dazu, dass alle MFC/OLE-Zwischenablage-Vorgänge fehlschlagen. Beim Bearbeiten des Codes zum Entfernen von Abhängigkeiten auf **CreateNewName**, sollten Sie auch den Code, öffnet und schließt die Windows-Zwischenablage, entfernen.  
  
```  
\oclient\mainview.cpp(332) : error C2065: 'AfxOleInsertDialog' : undeclared identifier  
\oclient\mainview.cpp(332) : error C2064: term does not evaluate to a function  
\oclient\mainview.cpp(344) : error C2057: expected constant expression  
\oclient\mainview.cpp(347) : error C2039: 'CreateNewObject' : is not a member of 'CRectItem'  
```  
  
 Diese Fehler Optimierungsfehler der **CMainView::OnInsertObject** Handler. Behandeln des Befehls "Neues Objekt einfügen" ist ein weiterer Bereich, in denen Dinge erheblich geändert haben. In diesem Fall ist es am einfachsten, einfach die ursprüngliche Implementierung mit derjenigen von AppWizard für eine neue OLE-Container-Anwendung zusammengeführt werden. Tatsächlich ist dies eine Technik, die zum Portieren von anderen Anwendungen angewendet werden können. In MFC/OLE1, Sie im Dialogfeld "Objekt einfügen" angezeigt, durch den Aufruf **AfxOleInsertDialog** Funktion. In dieser Version, die Sie erstellen eine **COleInsertObject** Dialogfeldobjekt und rufen `DoModal`. Darüber hinaus werden neue OLE-Elementen erstellt, mit einem **CLSID** anstelle einer Zeichenfolge Klassenname. Das Endergebnis sollte etwa wie folgt aussehen:  
  
```  
COleInsertDialog dlg;  
if (dlg.DoModal() != IDOK)  
    return; 
 
BeginWaitCursor();

 
CRectItem* pItem = NULL;  
TRY  
{ *// First create the C++ object  
    pItem = GetDocument()->CreateItem();
ASSERT_VALID(pItem);

 *// Initialize the item from the dialog data.  
    if (!dlg.CreateItem(pItem))  
    AfxThrowMemoryException();
*// any exception will do  
    ASSERT_VALID(pItem);

 *// run the object if appropriate  
    if (dlg.GetSelectionType() == 
    COleInsertDialog::createNewItem) 
    pItem->DoVerb(OLEIVERB_SHOW,
    this);

 *// update right away  
    pItem->UpdateLink();
pItem->UpdateItemRectFromServer();

 *// set selection to newly inserted item  
    SetSelection(pItem);

 pItem->Invalidate();

}  
CATCH (CException,
    e)  
{ *// clean up item  
    if (pItem != NULL)  
    GetDocument()->DeleteItem(pItem);

 
    AfxMessageBox(IDP_FAILED_TO_CREATE);

} 
END_CATCH  
 
EndWaitCursor();
```  
  
> [!NOTE]
>  Neues Objekt einfügen möglicherweise für Ihre Anwendung unterschiedlich sein):  
  
 Es ist auch erforderlich, gehören \<afxodlgs.h >, enthält die Deklaration für die **COleInsertObject** Dialogfeldklasse als auch die andere von MFC bereitgestellten Standarddialoge.  
  
```  
\oclient\mainview.cpp(367) : error C2065: 'OLEVERB_PRIMARY' : undeclared identifier  
\oclient\mainview.cpp(367) : error C2660: 'DoVerb' : function does not take 1 parameters  
```  
  
 Diese Fehler werden durch die Tatsache, die dass einige OLE1 Konstanten in OLE 2 geändert haben verursacht, obwohl Konzept sie identisch sind. In diesem Fall **OLEVERB_PRIMARY** hat sich geändert, um `OLEIVERB_PRIMARY`. Primäre Verb wird von einem Container, OLE1 sowohl OLE 2 in der Regel ausgeführt, wenn der Benutzer auf ein Element doppelklickt.  
  
 Darüber hinaus `DoVerb` jetzt einen zusätzlichen Parameter akzeptiert: einen Zeiger auf eine Sicht (`CView`*). Dieser Parameter wird nur verwendet, um "Visuelle Bearbeitung" (oder direkte Aktivierung) zu implementieren. Jetzt legen Sie diesen Parameter auf NULL, da Sie zu diesem Zeitpunkt nicht diese Funktion implementieren.  
  
 Um sicherzustellen, dass das Framework nie versucht, direkte aktivieren, sollten Sie überschreiben `COleClientItem::CanActivate` wie folgt:  
  
```  
BOOL CRectItem::CanActivate()  
{  
    return FALSE;  
}  
 
\oclient\rectitem.cpp(53) : error C2065: 'GetBounds' : undeclared identifier  
\oclient\rectitem.cpp(53) : error C2064: term does not evaluate to a function  
\oclient\rectitem.cpp(84) : error C2065: 'SetBounds' : undeclared identifier  
\oclient\rectitem.cpp(84) : error C2064: term does not evaluate to a function  
```  
  
 In MFC/OLE1 **COleClientItem::GetBounds** und **SetBounds** abgefragt und bearbeitet das Ausmaß eines Elements verwendet wurden (die **linken** und **oben**Mitglieder waren immer 0 (null)). In MFC/OLE 2 wird dies direkt von unterstützt `COleClientItem::GetExtent` und `SetExtent`, dem Umgang mit einer **Größe** oder `CSize` stattdessen.  
  
 Der Code für Ihre neue SetItemRectToServer und UpdateItemRectFromServer-Aufrufe wie folgt aussehen:  
  
```  
BOOL CRectItem::UpdateItemRectFromServer()  
{  
    ASSERT(m_bTrackServerSize);

 CSize size;  
    if (!GetExtent(&size))  
    return FALSE;    // blank  
 *// map from HIMETRIC to screen coordinates  
 {  
    CClientDC screenDC(NULL);

    screenDC.SetMapMode(MM_HIMETRIC);

 screenDC.LPtoDP(&size);

 } *// just set the item size  
    if (m_rect.Size() != size)  
 { *// invalidate the old size/position  
    Invalidate();
m_rect.right = m_rect.left + size.cx;  
    m_rect.bottom = m_rect.top + size.cy; *// as well as the new size/position  
    Invalidate();

 }  
    return TRUE;  
}  
 
BOOL CRectItem::SetItemRectToServer()  
{ *// set the official bounds for the embedded item  
    CSize size = m_rect.Size();

 {  
    CClientDC screenDC(NULL);

    screenDC.SetMapMode(MM_HIMETRIC);

 screenDC.DPtoLP(&size);

 }  
    TRY 
 {  
    SetExtent(size);
*// may do a wait  
 }  
    CATCH(CException, e)  
 {  
    return FALSE;  // links will not allow SetBounds  
 }  
    END_CATCH 
    return TRUE;  
}  
 
\oclient\frame.cpp(50) : error C2039: 'InWaitForRelease' : is not a member of 'COleClientItem'  
\oclient\frame.cpp(50) : error C2065: 'InWaitForRelease' : undeclared identifier  
\oclient\frame.cpp(50) : error C2064: term does not evaluate to a function  
```  
  
 In MFC/OLE1 synchrone API-Aufrufe aus einem Container mit einem Server wurden *simulierte*, da OLE1 grundsätzlich asynchron in vielen Fällen wurde. War es erforderlich, die vor der Verarbeitung von Befehlen, die vom Benutzer für einen ausstehenden asynchronen Aufruf in Bearbeitung zu überprüfen. MFC/OLE1 bereitgestellten der **COleClientItem::InWaitForRelease** -Funktion für die auf diese Weise. In MFC/OLE 2 ist dies nicht notwendig. so Sie um die Außerkraftsetzung der OnCommand alle zusammen im CMainFrame zu entfernen können.  
  
 An diesem Punkt wird OCLIENT kompilieren und verknüpfen.  
  
## <a name="other-necessary-changes"></a>Andere erforderlichen Änderungen  
 Es gibt einige Dinge, die nicht ausgeführt werden, die OCLIENT ausgeführt wird, jedoch beibehalten werden sollen. Es ist besser, diese jetzt statt später zu beheben.  
  
 Zunächst ist es erforderlich, um den OLE-Bibliotheken zu initialisieren. Dies erfolgt durch Aufrufen von **AfxOleInit** aus `InitInstance`:  
  
```  
if (!AfxOleInit())  
{  
    AfxMessageBox("Failed to initialize OLE libraries");

    return FALSE;  
}  
```  
  
 Es ist auch eine gute Idee, überprüfen Sie die virtuellen Funktionen für die Änderungen der Agentparameter. Eine solche Funktion wird `COleClientItem::OnChange`, außer Kraft gesetzte in jeder MFC/OLE-Container-Anwendung. Durch einen Blick auf Onlinehilfe, sehen Sie sich, dass eine zusätzliche "DWORD DwParam hinzugefügt wurde. Die neue CRectItem::OnChange sieht wie folgt aus:  
  
```  
void   
CRectItem::OnChange(OLE_NOTIFICATION wNotification, DWORD dwParam)  
{  
    if (m_bTrackServerSize&& 
 !UpdateItemRectFromServer())  
 { *// Blank object  
    if (wNotification == OLE_CLOSED)  
 { *// no data received for the object - destroy it  
    ASSERT(!IsVisible());

 GetDocument()->DeleteItem(this);

    return; // no update (item is gone now)  
 }  
 }  
    if (wNotification != OLE_CLOSED)  
    Dirty();
Invalidate();
*// any change will cause a redraw  
}  
```  
  
 In MFC/OLE1, containeranwendungen der Dokumentklasse aus abgeleiteten **COleClientDoc**. In MFC/OLE 2 diese Klasse wurde entfernt und ersetzt durch `COleDocument` (diese neuen Organisation erleichtert es, Container/Server-Anwendungen zu erstellen). Besteht eine `#define` ordnet **COleClientDoc** auf `COleDocument` zum Portieren von MFC/OLE1-Anwendungen zu MFC/OLE 2, z. B. OCLIENT vereinfachen. Eine der Funktionen, die nicht vom `COleDocument` , die vom bereitgestellt wurde **COleClientDoc** wird die Nachricht Standardbefehls-Zuordnungseinträge. Dies geschieht dies, auch serveranwendungen `COleDocument` (indirekt), wird nicht ausgeführt mit ihnen den Mehraufwand für diese Befehlshandler, wenn sie einer Container/Server-Anwendung sind. Sie müssen die meldungszuordnung CMainDoc die folgenden Einträge hinzu:  
  
```  
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE,
    OnUpdatePasteMenu)  
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE_LINK,
    OnUpdatePasteLinkMenu)  
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_LINKS,
    OnUpdateEditLinksMenu)  
ON_COMMAND(ID_OLE_EDIT_LINKS,
    COleDocument::OnEditLinks)  
ON_UPDATE_COMMAND_UI(ID_OLE_VERB_FIRST,
    OnUpdateObjectVerbMenu)  
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_CONVERT,
    OnUpdateObjectVerbMenu)  
ON_COMMAND(ID_OLE_EDIT_CONVERT,
    OnEditConvert)  
```  
  
 Die Implementierung dieser Befehle wird `COleDocument`, dies ist die Basisklasse für das Dokument.  
  
 An diesem Punkt ist OCLIENT eine funktionale OLE-Container-Anwendung. Es kann zum Einfügen von Elementen eines beliebigen Typs (OLE1 oder OLE 2). Da nicht der erforderlichen Code für die direkte Aktivierung implementiert wird, werden Elemente in einem separaten Fenster ähnlich wie mit OLE1 bearbeitet. Im nächste Abschnitt erläutert die notwendigen Änderungen vor, um die direkte Bearbeitung (manchmal als "Visuelle Bearbeitung" bezeichnet) zu aktivieren.  
  
## <a name="adding-visual-editing"></a>Hinzufügen von "Visuelle Bearbeitung"  
 Eine der interessantesten Funktionen von OLE ist die direkte Aktivierung (oder "Visuelle Bearbeitung"). Diese Funktion ermöglicht die Serveranwendung Teile der Benutzeroberfläche des Containers übernehmen eine nahtlosere Bearbeitung Schnittstelle für den Benutzer zur Verfügung gestellt. Um OCLIENT direkte Aktivierung implementieren zu können, müssen einige speziellen Ressourcen sowie zusätzlicher Code hinzugefügt werden. Diese Ressourcen und der Code werden normalerweise von AppWizard bereitgestellt – großer Anteil des Codes Hier wurde in der Tat geliehener direkt aus einer frischen AppWizard-Anwendung mit Unterstützung für "Container".  
  
 Erstens ist es erforderlich, fügen eine Menüressource verwendet werden, wenn es ist ein Element der in-Place aktiv ist. Sie können diese zusätzlichen Menüressource in Visual C++ erstellen, durch Kopieren die Ressource IDR_OCLITYPE und entfernt alle bis auf die Datei und Fenster-Popups. Zwei Trennlinien zwischen der Datei und Fenster Popups an, dass die Trennung zwischen Gruppen eingefügt (er sollte wie folgt aussehen: Datei &#124; &#124; Fenster). Was bedeuten, dass diese Trennzeichen und wie der Server und-Container Menüs zusammengeführt werden weitere Informationen finden Sie unter "Menüs und Ressourcen: Menüs schachteln" in *OLE 2 Klassen*.  
  
 Nachdem Sie mithilfe dieser Menüs erstellt haben, müssen Sie das Framework erfahren können. Dies erfolgt durch Aufrufen von `CDocTemplate::SetContainerInfo` für Dokumentvorlage, bevor Sie ihn der Liste der Dokument-Vorlage in die InitInstance hinzufügen. Der neue Code zum Registrieren der Dokumentvorlage sieht folgendermaßen aus:  
  
```  
CDocTemplate* pTemplate = new CMultiDocTemplate(
    IDR_OLECLITYPE, 
    RUNTIME_CLASS(CMainDoc), 
    RUNTIME_CLASS(CMDIChildWnd), // standard MDI child frame  
    RUNTIME_CLASS(CMainView));

pTemplate->SetContainerInfo(IDR_OLECLITYPE_INPLACE);

AddDocTemplate(pTemplate);
```   
  
 Die IDR_OLECLITYPE_INPLACE-Ressource ist in Visual C++ erstellt die speziellen direktes-Ressource.  
  
 Um die direkte Aktivierung zu ermöglichen, es gibt einige Dinge, die in beiden ändern müssen die `CView` (CMainView) abgeleitete Klasse als auch die `COleClientItem` abgeleitete Klasse (CRectItem). Alle diese Außerkraftsetzungen von AppWizard bereitgestellt werden, und ein Großteil der Implementierung direkt aus einer Anwendung der Standard-AppWizard stammen.  
  
 Im ersten Schritt dieses Ports direkte Aktivierung deaktiviert wurde, vollständig durch Außerkraftsetzen `COleClientItem::CanActivate`. Diese Überschreibung sollte entfernt werden, um die direkte Aktivierung zu ermöglichen. Darüber hinaus wurde NULL übergeben, um alle Aufrufe an `DoVerb` (es gibt zwei Spalten vorhanden), da die Ansicht nur für die direkte Aktivierung erforderlich war. Um die direkte Aktivierung vollständig zu implementieren, es ist notwendig, übergeben Sie die richtige Ansicht in der `DoVerb` aufrufen. Eine dieser Aufrufe ist **CMainView::OnInsertObject**:  
  
```  
pItem->DoVerb(OLEIVERB_SHOW, this);
```  
  
 Ein weiterer Vorteil ist **CMainView::OnLButtonDblClk**:  
  
```  
m_pSelection->DoVerb(OLEIVERB_PRIMARY, this);
```  
  
 Es ist erforderlich, außer Kraft setzen `COleClientItem::OnGetItemPosition`. Dies weist den Server, wo das Fenster relativ zum Fenster des Containers eingefügt werden, wenn das Element aktiviert ist. Für OCLIENT ist die Implementierung trivial:  
  
```  
void CRectItem::OnGetItemPosition(CRect& rPosition)  
{  
    rPosition = m_rect;  
}  
```  
  
 Die meisten Server implementieren darüber hinaus den so genannten "Direktes Ändern der Größe." Dadurch wird das Serverfenster, Größe und verschoben, während der Benutzer das Element bearbeitet werden. Der Container muss diese Aktion teilnehmen, da verschieben oder Ändern der Größe des Fensters in der Regel die Position und Größe innerhalb des Containerdokuments, selbst auswirkt. Die Implementierung für OCLIENT synchronisiert die internen Rechteck von M_rect mit der neuen Position und Größe verwaltet.  
  
```  
BOOL CRectItem::OnChangeItemPosition(const CRect& rectPos)  
{  
    ASSERT_VALID(this);

 
    if (!COleClientItem::OnChangeItemPosition(rectPos))  
    return FALSE;  
 
    Invalidate();
m_rect = rectPos;  
    Invalidate();
GetDocument()->SetModifiedFlag();

 
    return TRUE;  
}  
```  
  
 Zu diesem Zeitpunkt besteht so viel Code zu einem Element zum direkten aktiviert werden und für den Umgang mit größenanpassung und verschieben das Element aus, wenn er aktiv ist, aber kein Code ermöglicht dem Benutzer, um die Sitzung zur Bearbeitung zu beenden. Obwohl einige Server diese Funktionen sind selbst werden durch behandeln die ESC-Taste, wird vorgeschlagen,-Container ermöglichen die zwei Möglichkeiten, ein Element zu deaktivieren: (1) durch Klicken das Element, und (2) durch Drücken der ESC-Taste.  
  
 Für die ESC-Taste Hinzufügen einer Zugriffstaste mit Visual C++, die die Taste "VK_ESCAPE" bezeichnet einen Befehl zugeordnet, ID_CANCEL_EDIT wird auf die Ressourcen hinzugefügt. Der Handler für diesen Befehl lautet folgendermaßen:  
  
```  
// The following command handler provides the standard  
// keyboard user interface to cancel an in-place  
// editing session.void CMainView::OnCancelEdit()  
{ *// Close any in-place active item on this view.  
    COleClientItem* pActiveItem = 
    GetDocument()->GetInPlaceActiveItem(this);

 if (pActiveItem != NULL)  
    pActiveItem->Close();
ASSERT(GetDocument()->GetInPlaceActiveItem(this) == NULL);

}  
```  
  
 Um Fälle zu behandeln, in denen der Benutzer, außerhalb des Elements klickt, fügen Sie den folgenden Code am Anfang des **CMainView::SetSelection**:  
  
```  
if (pNewSel != m_pSelection || pNewSel == NULL)  
{  
    COleClientItem* pActiveItem = 
    GetDocument()->GetInPlaceActiveItem(this);

 if (pActiveItem != NULL&& pActiveItem != pNewSel)  
    pActiveItem->Close();

} 
 
```  
  
 Wenn ein Element in-Place aktiv ist, sollte es den Fokus haben. Sie behandeln OnSetFocus, damit Sie den Fokus immer zum aktiven Element übertragen wird, wenn die Sicht den Fokus erhält, stellen Sie sicher, dass dies der Fall ist:  
  
```  
// Special handling of OnSetFocus and OnSize are required   
// when an object is being edited in-place.  
void CMainView::OnSetFocus(CWnd* pOldWnd)  
{  
    COleClientItem* pActiveItem = 
    GetDocument()->GetInPlaceActiveItem(this);

 if (pActiveItem != NULL&& 
    pActiveItem->GetItemState() == COleClientItem::activeUIState)  
 { *// need to set focus to this item if it is same view  
    CWnd* pWnd = pActiveItem->GetInPlaceWindow();
if (pWnd != NULL)  
 {  
    pWnd->SetFocus();
*// don't call the base class  
    return; 
 }  
 }  
 
    CView::OnSetFocus(pOldWnd);

} 
```  
  
 Beim Ändern der Größe der Sicht, müssen Sie das aktive Element zu benachrichtigen, das dass das Clippingrechteck geändert hat. Hierzu geben Sie einen Handler für `OnSize`:  
  
```  
void CMainView::OnSize(UINT nType,
    int cx,
    int cy)  
{  
    CView::OnSize(nType,
    cx,
    cy);

    COleClientItem* pActiveItem = 
    GetDocument()->GetInPlaceActiveItem(this);

 if (pActiveItem != NULL)  
    pActiveItem->SetItemRects();

} 
```  
  
## <a name="case-study-hiersvr-from-mfc-20"></a>Fallstudie: HIERSVR von MFC 2.0  
 [HIERSVR](../visual-cpp-samples.md) wurde auch in MFC 2.0 enthalten und mit MFC/OLE1 OLE implementiert. Dieser Hinweis beschreibt kurz die Schritte, mit denen diese Anwendung zunächst konvertiert wurde, um die Klassen von MFC/OLE 2 verwenden. Eine Reihe von Funktionen wurden hinzugefügt, nachdem der erste Port abgeschlossen wurde, um die Klassen von MFC/OLE 2 besser zu veranschaulichen. Diese Funktionen werden hier nicht behandelt; finden Sie im Beispiel für Weitere Informationen zu diesen erweiterten Funktionen.  
  
> [!NOTE]
>  Die Compiler-Fehler und die schrittweise wurde mit Visual C++-2.0 erstellt. Bestimmte Fehlermeldungen und Speicherorte mit Visual C++ 4.0 geändert haben, jedoch bleibt gültig, die konzeptionelle Informationen.  
  
## <a name="getting-it-up-and-running"></a>Einrichten des Projekts und ausführen  
 So portieren Sie das Beispiel HIERSVR zu MFC/OLE-Ansatz ist, beginnt mit der Erstellung und beheben die offensichtliche Compilerfehler, die sich ergeben, werden. Wenn Sie im Beispiel HIERSVR MFC 2.0 dauern und kompilieren Sie ihn unter dieser Version von MFC, finden Sie, dass nicht viele Fehler zu beheben (obwohl es mehr als mit dem OCLIENT-Beispiel sind). Die Fehler in der Reihenfolge, in der sie in der Regel ausgeführt, werden nachfolgend beschrieben.  
  
## <a name="compile-and-fix-errors"></a>Kompilierung und Behebung von Fehlern  
  
```  
\hiersvr\hiersvr.cpp(83) : error C2039: 'RunEmbedded' : is not a member of 'COleTemplateServer'  
```  
  
 Diese erste Fehler zeigt an, die ein größeres Problem mit der `InitInstance` Funktion für Server. Die Initialisierung für einen OLE-Server erforderlich sind, ist wahrscheinlich eine der größten vorgenommenen Änderungen an Ihrer Anwendung MFC/OLE1 Bezugsquelle ausgeführt vornehmen müssen. Die beste Vorgehensweise ist betrachten, was AppWizard für einen OLE-Server erstellt, und ändern den Code entsprechend. Hier sind einige Punkte zu bedenken:  
  
 Es ist notwendig, die durch Aufrufen die OLE-Bibliotheken initialisieren **AfxOleInit**  
  
 Rufen Sie SetServerInfo auf das Dokumentvorlagenobjekt festzulegende Ressource verarbeitet und Laufzeit-Klasseninformationen, die Sie mit festlegen können die `CDocTemplate` Konstruktor.  
  
 Das Hauptfenster der Anwendung nicht angezeigt werden, wenn Embedding in der Befehlszeile vorhanden ist.  
  
 Sie müssen eine **GUID** für das Dokument. Dies ist ein eindeutiger Bezeichner für den Dokumenttyp (128 Bit). AppWizard erstellt für Sie – Wenn Sie hier das beschriebene Verfahren verwenden, kopieren Sie den neuen Code aus einer neuen Serveranwendung von AppWizard generiert, Sie können einfach "stehlen" die GUID über diese Anwendung. Wenn dies nicht der Fall ist, können Sie die GUIDGEN. EXE-Dienstprogramm in das Verzeichnis "bin".  
  
 Es ist notwendig, die "connect" Ihre `COleTemplateServer` Objekt, das durch Aufrufen der Dokumentvorlage `COleTemplateServer::ConnectTemplate`.  
  
 Aktualisieren Sie die Registrierung, wenn Ihre Anwendung eigenständigen ausgeführt wird. Wenn der Benutzer auf diese Weise die. EXE-Datei für Ihre Anwendung, von seiner neuen Position Ausführen der Windows-Registrierung Systemdatenbank, zeigen Sie auf den neuen Speicherort aktualisiert.  
  
 Nach dem Anwenden aller diese Änderungen, die basierend auf was AppWizard für erstellt `InitInstance`, die `InitInstance` (und zugehörigen GUID) für HIERSVR sollte wie folgt aussehen:  
  
```  
// this is the GUID for HIERSVR documents  
static const GUID BASED_CODE clsid = 
 { 0xA0A16360L,
    0xC19B,
    0x101A, { 0x8C,
    0xE5,
    0x00,
    0xDD,
    0x01,
    0x11,
    0x3F,
    0x12 } };  
 
/////////////////////////////////////////////////////////////////////////////  
// COLEServerApp initialization  
 
BOOL COLEServerApp::InitInstance()  
{ *// OLE 2 initialization  
    if (!AfxOleInit())  
 {  
    AfxMessageBox("Initialization of the OLE failed!");

    return FALSE;  
 }  
 *// Standard initialization  
    LoadStdProfileSettings();

// Load standard INI file options   
 *// Register document templates  
    CDocTemplate* pDocTemplate;  
    pDocTemplate = new CMultiDocTemplate(IDR_HIERSVRTYPE,  
    RUNTIME_CLASS(CServerDoc), 
    RUNTIME_CLASS(CMDIChildWnd), 
    RUNTIME_CLASS(CServerView));

 pDocTemplate->SetServerInfo(IDR_HIERSVRTYPE_SRVR_EMB);

    AddDocTemplate(pDocTemplate);

 *// create main MDI Frame window  
    CMainFrame* pMainFrame = new CMainFrame;  
    if (!pMainFrame->LoadFrame(IDR_MAINFRAME))  
    return FALSE;  
    m_pMainWnd = pMainFrame;  
 
    SetDialogBkColor();
*// gray look  
 *// enable file manager drag/drop and DDE Execute open  
    m_pMainWnd->DragAcceptFiles();
EnableShellOpen();

 
    m_server.ConnectTemplate(clsid,
    pDocTemplate,
    FALSE);

    COleTemplateServer::RegisterAll();

 *// try to launch as an OLE server  
    if (RunEmbedded())  
 { *// "short-circuit" initialization -- run as server!  
    return TRUE;  
 }  
    m_server.UpdateRegistry();
RegisterShellFileTypes();

 *// not run as OLE server,
    so show the main window  
    if (m_lpCmdLine[0] == '\0')  
 { *// create a new (empty) document  
    OnFileNew();

 }  
    else 
 { *// open an existing document  
    OpenDocumentFile(m_lpCmdLine);

 }  
 
    pMainFrame->ShowWindow(m_nCmdShow);

 pMainFrame->UpdateWindow();

 
    return TRUE;  
}  
```  
  
 Beachten Sie, dass der obige Code auf eine neue Ressourcen-ID, IDR_HIERSVRTYPE_SRVR_EMB bezieht. Dies ist die Menüressource verwendet werden, wenn ein Dokument, das in einem anderen Container eingebettet ist bearbeitet wird. In MFC/OLE1 wurden die Menüelemente, die spezifisch für ein eingebettetes Element bearbeiten dynamisch geändert. Verwenden eine vollkommen andere Menüstruktur beim Bearbeiten von eines eingebetteten Elements anstelle von dateibasierten Dokument bearbeiten erleichtert diese zwei Modi unterschiedliche Benutzeroberflächen bereit. Wie Sie sehen werden, wird ein eingebettetes Objekt direkte Bearbeitung einer vollständig separaten Menüressource verwendet.  
  
 Um diese Ressource zu erstellen, laden Sie das Ressourcenskript in Visual C++, und kopieren Sie die vorhandene IDR_HIERSVRTYPE Menüressource. Benennen Sie die neue Ressource in IDR_HIERSVRTYPE_SRVR_EMB (Dies ist dieselbe Namenskonvention, die von AppWizard verwendet). Als Nächstes ändern Sie "Speichern", "Update der Datei"; Geben Sie ihm die Befehls-ID **ID_FILE_UPDATE**. Ändern Sie auch "Datei speichern unter" in "Datei Kopie speichern unter"; Geben Sie ihm die Befehls-ID **ID_FILE_SAVE_COPY_AS**. Das Framework bietet die Implementierung von beide Befehle.  
  
```  
\hiersvr\svritem.h(60) : error C2433: 'OLESTATUS' : 'virtual' not permitted on data declarations  
\hiersvr\svritem.h(60) : error C2501: 'OLESTATUS' : missing decl-specifiers  
\hiersvr\svritem.h(60) : error C2146: syntax error : missing ';' before identifier 'OnSetData'  
\hiersvr\svritem.h(60) : error C2061: syntax error : identifier 'OLECLIPFORMAT'  
\hiersvr\svritem.h(60) : error C2501: 'OnSetData' : missing decl-specifiers  
```  
  
 Es gibt diverse aufgetretene Fehler die Außerkraftsetzung der `OnSetData`, da er verweist die **OLESTATUS** Typ. **OLESTATUS** war der OLE1 Fehler zurückgegebenen. Dies hat sich geändert, um `HRESULT` in OLE 2, obwohl MFC in der Regel konvertiert ein `HRESULT` in einer `COleException` , die den Fehler enthält. In diesem Fall die Außerkraftsetzung der `OnSetData` ist nicht mehr erforderlich, daher ist die einfachste Vorgehensweise zu entfernen.  
  
```  
\hiersvr\svritem.cpp(30) : error C2660: 'COleServerItem::COleServerItem' : function does not take 1 parameters  
```  
  
 Die `COleServerItem` Konstruktor nimmt einen zusätzlichen 'BOOL'-Parameter. Dieses Flag gibt an, wie die Verwaltung des Arbeitsspeichers auf erfolgt die `COleServerItem` Objekte. Durch Festlegen auf "true", das Framework die Speicherverwaltung dieser Objekte verarbeitet – gelöscht werden, wenn sie nicht mehr benötigt werden. HIERSVR verwendet **CServerItem** (abgeleitet von `COleServerItem`) Objekte als Teil seiner eigenen Daten, damit Sie dieses Flag auf "false" festgelegt werden. Auf diese Weise können HIERSVR zu bestimmen, wenn jedes Serverelement gelöscht wird.  
  
```  
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class  
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class  
```  
  
 Wie diese Fehler vermuten lassen, sind einige "rein virtuell" Funktionen, die nicht in CServerItem überschrieben wurden. Dies wird wahrscheinlich durch den Umstand verursacht, die OnDraws Parameterliste geändert wurde. Ändern Sie zum Beheben dieses Fehlers **CServerItem:: OnDraw** (sowie die Deklaration in svritem.h) wie folgt:  
  
```  
BOOL CServerItem::OnDraw(CDC* pDC,
    CSize& rSize)  
{ *// request from OLE to draw node  
    pDC->SetMapMode(MM_TEXT);

// always in pixels  
    return DoDraw(pDC,
    CPoint(0,
    0),
    FALSE);

}  
```  
  
 Der neue Parameter ist "rSize". Wenn einfache haben, können Sie in der der Zeichnung ausfüllen. Diese Größe muss **HIMETRIC**. In diesem Fall es ist nicht praktisch, füllen Sie diesen Wert im, damit das Framework ruft `OnGetExtent` zum Abrufen des Wertebereichs. Damit dies funktioniert, stehen Ihnen implementieren `OnGetExtent`:  
  
```  
BOOL CServerItem::OnGetExtent(DVASPECT dwDrawAspect,
    CSize& rSize)  
{  
    if (dwDrawAspect != DVASPECT_CONTENT)  
    return COleServerItem::OnGetExtent(dwDrawAspect,
    rSize);

 
    rSize = CalcNodeSize();
return TRUE;  
}  
 
\hiersvr\svritem.cpp(104) : error C2065: 'm_rectBounds' : undeclared identifier  
\hiersvr\svritem.cpp(104) : error C2228: left of '.SetRect' must have class/struct/union type  
\hiersvr\svritem.cpp(106) : error C2664: 'void __pascal __far DPtoLP(struct ::tagPOINT __far *,
    int)__far const ' : cannot convert parameter 1 from 'int __far *' to 'struct ::tagPOINT __far *'  
```  
  
 In der CServerItem::CalcNodeSize-Funktion wird die Elementgröße in konvertiert **HIMETRIC** und gespeicherte in **M_rectBounds**. Die nicht dokumentiert "**M_rectBounds**" Mitglied `COleServerItem` ist nicht vorhanden (er wurde teilweise durch ersetzt `m_sizeExtent`, aber in OLE 2 dieser Member besitzt eine etwas andere Verwendung als **M_rectBounds**OLE1 haben). Anstatt durch die Einstellung der **HIMETRIC** Größe in diese Membervariable wird es zurückgegeben. Dieser Rückgabewert wird verwendet, `OnGetExtent`, zuvor implementiert.  
  
```  
CSize CServerItem::CalcNodeSize()  
{  
    CClientDC dcScreen(NULL);

 
    m_sizeNode = dcScreen.GetTextExtent(m_strDescription,  
    m_strDescription.GetLength());

 m_sizeNode += CSize(CX_INSET* 2,
    CY_INSET* 2);

 *// set suggested HIMETRIC size  
    CSize size(m_sizeNode.cx,
    m_sizeNode.cy);

    dcScreen.SetMapMode(MM_HIMETRIC);

 dcScreen.DPtoLP(&size);

    return size;  
}  
```  
  
 CServerItem überschreibt auch **COleServerItem::OnGetTextData**. Diese Funktion ist in MFC/OLE veraltet und wird durch einen anderen Mechanismus ersetzt. Die MFC 3.0-Version von MFC-OLE-Beispiel [HIERSVR](../visual-cpp-samples.md) implementiert diese Funktionalität durch Außerkraftsetzen von `COleServerItem::OnRenderFileData`. Diese Funktionalität ist nicht für diesen grundlegenden Port wichtig, damit Sie die Außerkraftsetzung OnGetTextData entfernen können.  
  
 Es gibt viele weitere Fehler in svritem.cpp nicht behandelt wurde. Sie sind nicht "real" Fehler: nur Fehler, die durch vorherige Fehler verursacht.  
  
```  
\hiersvr\svrview.cpp(325) : error C2660: 'CopyToClipboard' : function does not take 2 parameters  
```  
  
 `COleServerItem::CopyToClipboard` unterstützt nicht mehr das Flag "bIncludeNative" ein. Die systemeigenen Daten (die Daten geschrieben, indem die Serverelement Serialize-Funktion) ist immer kopiert, damit Sie den ersten Parameter entfernen. Darüber hinaus `CopyToClipboard` wird eine Ausnahme ausgelöst, wenn ein Fehler tritt auf, anstatt Sie "false". Ändern Sie den Code für CServerView::OnEditCopy wie folgt:  
  
```  
void CServerView::OnEditCopy()  
{  
    if (m_pSelectedNode == NULL)  
    AfxThrowNotSupportedException();

 
    TRY 
 {  
    m_pSelectedNode->CopyToClipboard(TRUE);

 }  
    CATCH_ALL(e) 
 {  
    AfxMessageBox("Copy to clipboard failed");

 }  
    END_CATCH_ALL 
}  
```  
  
 Weitere aufgetretene Fehler der Kompilierung der HIERSVR-Version 2.0 von MFC als gab es die gleiche Version von OCLIENT waren, gab es tatsächlich weniger Änderungen.  
  
 An diesem Punkt wird HIERSVR kompilieren und verknüpfen und fungieren als OLE-Server, aber ohne die Bearbeitung direktes-Funktion, die als Nächstes implementiert werden.  
  
## <a name="adding-visual-editing"></a>Hinzufügen von "Visuelle Bearbeitung"  
 Um diese Serveranwendung "Visuelle Bearbeitung" (oder direkte Aktivierung) hinzuzufügen, gibt es nur ein paar Dinge, denen Sie erledigen müssen:  
  
-   Sie benötigen eine spezielle Menüressource verwendet werden, wenn das Element in-Place aktiv ist.  
  
-   Diese Anwendung weist eine Symbolleiste, damit Sie benötigen eine Symbolleiste mit nur einen Teil der normalen Symbolleiste aus, um die Befehle im Menü auf dem Server verfügbar (Übereinstimmung mit den oben genannten Menüressource) übereinstimmen.  
  
-   Benötigen Sie eine neue Klasse abgeleitet `COleIPFrameWnd` , der die direkte Benutzeroberfläche bereitstellt (ähnlich wie CMainFrame abgeleitet `CMDIFrameWnd`, bietet der MDI-Benutzeroberfläche).  
  
-   Sie müssen das Framework über diese speziellen Ressourcen und Klassen zu informieren.  
  
 Die Menüressource ist einfach zu erstellen. Führen Sie Visual C++, kopieren Sie die Menüressource IDR_HIERSVRTYPE in einer Menüressource IDR_HIERSVRTYPE_SRVR_IP aufgerufen. Ändern Sie im Menü aus, sodass nur für die Verwendung der Bearbeiten und Hilfe im Menü Popups übrig sind. Hinzufügen von zwei Trennzeichen zum Menü zwischen der Menüs bearbeiten und Hilfe (er sollte wie folgt aussehen: Bearbeiten &#124; &#124; -Hilfe). Weitere Informationen zu der Bedeutung dieser Trennzeichen und wie der Server und-Container Menüs zusammengeführt werden, finden Sie unter "Menüs und Ressourcen: Menüs schachteln" in *OLE 2 Klassen*.  
  
 Die Bitmap für die Teilmenge-Symbolleiste kann problemlos erstellt werden, durch Kopieren die Version auf eine neue AppWizard generierte Anwendung mit der Option "Server" überprüft. Diese Bitmap kann dann in Visual C++ importiert werden. Achten Sie darauf, dass Sie der Bitmap eine ID IDR_HIERSVRTYPE_SRVR_IP erteilen.  
  
 Abgeleitete Klasse von `COleIPFrameWnd` aus einer Anwendung generierten AppWizard mit Serversupport sowie kopiert werden können. Kopieren Sie beide Dateien, IPFRAME. CPP und IPFRAME. H und fügen sie dem Projekt hinzu. Stellen Sie sicher, dass die `LoadBitmap` Aufruf bezieht sich auf IDR_HIERSVRTYPE_SRVR_IP, die Bitmap, die im vorherigen Schritt erstellt haben.  
  
 Nun, da die neue Ressourcen und Klassen erstellt werden, fügen Sie den erforderlichen Code, sodass das Framework diese kennt (und weiß, dass diese Anwendung jetzt direkte Bearbeitung unterstützt). Dies geschieht, indem Sie einige weitere Parameter zum Hinzufügen der `SetServerInfo` rufen Sie in der `InitInstance` Funktion:  
  
```  
pDocTemplate->SetServerInfo(IDR_HIERSVRTYPE_SRVR_EMB,  
    IDR_HIERSVRTYPE_SRVR_IP,
    RUNTIME_CLASS(CInPlaceFrame));
```  
  
 Sie kann jetzt zum direkten ausführen in einem Container, der auch die direkte Aktivierung unterstützt. Es gibt jedoch eine kleinere Fehler, die der Code weiterhin sein. HIERSVR unterstützt ein Kontextmenü angezeigt, wenn der Benutzer die rechte Maustaste drückt. Dieses Menü funktioniert, wenn HIERSVR vollständig geöffnet ist, aber funktioniert nicht, wenn Sie ein Einbetten von direktes Bearbeiten. Der Grund kann auf diese einzelne Codezeile in CServerView::OnRButtonDown festgesetzt werden:  
  
```  
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,  
    point.x,
    point.y,
    AfxGetApp()->m_pMainWnd);
```  
  
 Beachten Sie den Verweis auf **AfxGetApp() -> M_pMainWnd**. Wenn der Server direktes aktiviert ist, er verfügt über ein Hauptfenster und M_pMainWnd festgelegt ist, aber er ist in der Regel nicht sichtbar. Darüber hinaus kann in diesem Fenster auf die *main* Fenster der Anwendung, die angezeigt wird, wenn der Server vollständig ist MDI-Rahmenfenster öffnen oder eigenständig ausgeführt. Verweist nicht auf das Fenster des aktiven Frames – die beim direkten aktiviert ist ein Fenster abgeleitet `COleIPFrameWnd`. Um das richtige aktive Fenster zu erhalten, selbst wenn die direkte Bearbeitung dieser Version von MFC fügt eine neue Funktion hinzu `AfxGetMainWnd`. Im Allgemeinen sollten Sie diese Funktion statt des verwenden **AfxGetApp() -> M_pMainWnd**. Dieser Code muss wie folgt ändern:  
  
```  
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,  
    point.x,
    point.y,
    AfxGetMainWnd());
```  
  
 Sie haben jetzt einen OLE-Server, die minimal für die funktionale direkte Aktivierung aktiviert. Es sind jedoch noch viele Funktionen verfügbar mit MFC/OLE 2, die in MFC/OLE1 nicht verfügbar waren. Finden Sie im Beispiel HIERSVR Weitere Ideen auf Funktionen, die Sie möglicherweise implementieren möchten. Einige der Funktionen, die HIERSVR implementiert sind unten aufgeführt:  
  
-   Vergrößern/verkleinern, für "true" WYSIWYG-Verhalten in Bezug auf den Container.  
  
-   Ziehen Sie / löschen und eine benutzerdefinierte Zwischenablageformat.  
  
-   Durchführen eines Bildlaufs Containerfenster als Auswahl geändert wird.  
  
 Das HIERSVR-Beispiel in MFC 3.0 verwendet auch einen etwas anderen Entwurf für den Server-Elementen. Dadurch wird Speicherplatz gespart und Ihre Verknüpfungen flexibler. Mit der Version 2.0 HIERSVR jeden Knoten in der Struktur *ist eine* `COleServerItem`. `COleServerItem` führt ein wenig mehr Aufwand als unbedingt erforderlich für jeden dieser Knoten ist jedoch ein `COleServerItem` für jeden aktiven Link ist erforderlich. Jedoch größtenteils, gibt es nur sehr wenige aktive Links zu einem beliebigen Zeitpunkt. Um dies effizienter zu gestalten, trennt der HIERSVR in dieser Version von MFC den Knoten aus der `COleServerItem`. Es weist sowohl ein CServerNode und ein **CServerItem** Klasse. Die **CServerItem** (abgeleitet von `COleServerItem`) wird nur bei Bedarf erstellt. Nachdem den (oder die Container) diesen bestimmten Link zu diesem bestimmten Knoten verwenden beenden, ist das CServerItem-Objekt, das die CServerNode zugeordneten gelöscht. Dieser Entwurf wird effizienter und flexibler. Seine Flexibilität ist beim Umgang mit mehreren Auswahl Links. Keiner dieser beiden Versionen von HIERSVR Mehrfachauswahl unterstützt, aber wäre es viel einfacher, hinzufügen (und Links zu solchen Auswahl unterstützen) mit der MFC 3.0-Version von HIERSVR, da die `COleServerItem` von systemeigenen Daten getrennt ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

