---
title: 'TN041: MFC-OLE1-Migration zu MFC-OLE 2'
ms.date: 10/18/2018
f1_keywords:
- vc.mfc.ole
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
ms.openlocfilehash: b398a1adbf2f47343eed076f32ade5bb2564cd52
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58767976"
---
# <a name="tn041-mfcole1-migration-to-mfcole-2"></a>TN041: MFC/OLE1-Migration zu MFC/OLE 2

> [!NOTE]
> Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

## <a name="general-issues-relating-to-migration"></a>Allgemeine Probleme im Zusammenhang mit der Migration

Eines der Entwurfsziele für die OLE 2-Klassen in MFC 2.5 (und höher) war ein Großteil der Architektur fügen Sie in der für ein OLE-1.0-Unterstützung in MFC 2.0 erfolgen beibehalten werden sollen. Daher viele der gleichen OLE-Klassen in MFC 2.0 noch vorhanden sind in dieser Version von MFC (`COleDocument`, `COleServerDoc`, `COleClientItem`, `COleServerItem`). Darüber hinaus sind viele der APIs in diesen Klassen genau identisch. Unterscheidet sich jedoch OLE 2 erheblich von OLE-1,0, damit Sie erwarten können, dass einige Details geändert haben. Wenn Sie mit der Unterstützung von MFC 2.0 OLE1 vertraut sind, werden Sie mit MFC 2.0-Unterstützung zu Hause fühlen.

Wenn Sie eine vorhandene MFC/OLE1-Anwendung erstellen und OLE 2-Funktionalität hinzugefügt wird, sollten Sie zunächst diesen Hinweis lesen. In diesem Hinweis werden einige allgemeine Probleme, die Sie möglicherweise beim Portieren Ihrer Funktionen zur OLE1 auf MFC/OLE 2 und anschließend wird erläutert, die Probleme beim Portieren von zwei Anwendungen, die in MFC 2.0 enthaltenen im Detail behandelt: die MFC-OLE-Beispiele [OCLIENT](../overview/visual-cpp-samples.md) und [HIERSVR](../overview/visual-cpp-samples.md).

## <a name="mfc-documentview-architecture-is-important"></a>MFC Dokument-/Ansichtarchitektur ist wichtig

Wenn Ihre Anwendung ist nicht MFCs Dokument-/Ansichtarchitektur verwendet, und Sie OLE 2-Unterstützung für Ihre Anwendung hinzufügen möchten, ist jetzt die Zeit, in die Dokument-/Ansicht zu verschieben. Viele der Vorteile von MFC OLE 2-Klassen werden nur realisiert, sobald Ihre Anwendung die integrierte Architektur und Komponenten von MFC verwendet.

Implementieren einen Server oder den Container ohne Verwendung der MFC-Architektur ist möglich, aber nicht empfehlenswert.

## <a name="use-mfc-implementation-instead-of-your-own"></a>Verwenden Sie MFC-Implementierung, anstatt Ihre eigenen

MFC-"vorprogrammierten Implementierung" Klassen wie z. B. `CToolBar`, `CStatusBar`, und `CScrollView` integrierte Groß-/Kleinschreibung speziellen Code für die Unterstützung von OLE 2 haben. Bei Verwendung dieser Klassen in Ihrer Anwendung müssen Sie also von den Aufwand, fügen sie auf diesen OLE aufmerksam zu machen profitieren. In diesem Fall ist es möglich, hier "Roll-your-own" Klassen für diese Zwecke, aber es wird nicht empfohlen. Wenn Sie eine ähnliche Funktionalität implementieren müssen, ist der MFC-Quellcode ein ausgezeichnetes Nachschlagewerk für den Umgang mit einigen feiner Punkte des OLE (insbesondere, wenn es darum geht, direktes Aktivierung).

## <a name="examine-the-mfc-sample-code"></a>Überprüfen Sie den Code der MFC-Beispiel

Es gibt eine Anzahl von MFC-Beispiele, die OLE-Funktionen enthalten. Jede dieser Anwendungen implementiert OLE aus einem anderen Winkel aus:

- [HIERSVR](../overview/visual-cpp-samples.md) hauptsächlich für den Einsatz als Serveranwendung vorgesehen. Es wurde war in MFC 2.0 als MFC/OLE1-Anwendung enthalten und zu MFC/OLE 2 portiert und dann erweitert, dass es viele OLE-Funktionen finden Sie in OLE 2 implementiert.

- [OCLIENT](../overview/visual-cpp-samples.md) Dies ist eine eigenständige containeranwendung, die viele der OLE-Funktionen vom Standpunkt der Container zeigen sollen. Es zu portiert wurde von MFC 2.0, und klicken Sie dann erweitert, um viele der der erweiterten OLE-Funktionen, z. B. das benutzerdefinierte Zwischenablageformate und Links zu eingebetteten Elemente unterstützen.

- [DRAWCLI](../overview/visual-cpp-samples.md) dieser Anwendung implementiert die Unterstützung von OLE-Container viel wie OCLIENT der Fall ist, mit dem Unterschied, dass es im Rahmen einer vorhandenen objektorientiertes Zeichenprogramm tut es. Sie erfahren Sie, wie Sie implementieren die Unterstützung von OLE-Container und in Ihre vorhandene Anwendung integrieren können.

- [SUPERPAD](../overview/visual-cpp-samples.md) dieser Anwendung als auch wird von einer eigenständigen Anwendung in Ordnung sind, ist auch ein OLE-Server. Die serverunterstützung,, es implementiert, ist ziemlich Entwurfsaufwand. Von besonderem Interesse ist, wie sie OLE-Zwischenablage-Diensten verwendet, um Daten in die Zwischenablage zu kopieren, aber verwendet die Funktionen in das Steuerelement für Windows "Bearbeiten", um Zwischenablage einfügen-Funktionalität zu implementieren. Dadurch wird eine interessante Mischung von herkömmlichen Windows-API-Verwendung sowie die Integration in die neue OLE-APIs.

Weitere Informationen zu Beispielanwendungen wählen können finden Sie unter der "MFC-Beispiel Help".

## <a name="case-study-oclient-from-mfc-20"></a>Fallstudie: OCLIENT von MFC 2.0

Wie weiter oben erläutert [OCLIENT](../overview/visual-cpp-samples.md) in MFC 2.0 enthalten war und OLE mit MFC/OLE1 implementiert. Die Schritte, die mit denen diese Anwendung anfänglich konvertiert wurde, um die MFC/OLE 2-Klassen verwenden, werden nachfolgend beschrieben. Eine Reihe von Funktionen wurden hinzugefügt, nachdem der erste Port abgeschlossen wurde, um die MFC/OLE-Klassen besser zu veranschaulichen. Diese Funktionen werden hier nicht behandelt; Das Beispiel selbst, um mehr über die erweiterten Features finden Sie unter.

> [!NOTE]
> Die c#-Compilerfehlern und schrittweise Anleitungen wurde mit Visual C++-2.0 erstellt. Fehlermeldungen und Speicherorte können mit Visual C++ 4.0 geändert haben, aber bleibt gültig, die konzeptionelle Informationen.

## <a name="getting-it-up-and-running"></a>Es einrichten und ausführen

Ansatz zum Portieren von OCLIENT zu MFC/OLE-Beispiel wird durch die Erstellung und Beheben der offensichtlichen Compilerfehler, die sich ergeben, werden gestartet. Wenn Sie verwenden Sie die OCLIENT von MFC 2.0 und kompilieren es unter dieser Version von MFC, finden Sie, dass es nicht, dass viele Fehler zu beheben. Die Fehler in der Reihenfolge, in der sie aufgetreten sind, werden unten beschrieben.

## <a name="compile-and-fix-errors"></a>Kompilieren und Beheben von Fehlern

```Output
\oclient\mainview.cpp(104) : error C2660: 'Draw' : function does not take 4 parameters
```

Der erste Fehler betrifft `COleClientItem::Draw`. In MFC/OLE1 benötigt mehr Parameter als die MFC/OLE-Version verwendet wurde. Die zusätzlichen Parameter wurden häufig nicht erforderlich und in der Regel NULL (wie in diesem Beispiel). Diese Version von MFC kann automatisch die Werte für die LpWBounds bestimmen, wenn CDC, die gezeichnet wird einer Metadatei Domänencontroller ist. Darüber hinaus ist der pFormatDC-Parameter nicht mehr erforderlich, da das Framework über das "Attribut DC" den pDC übergebenen erstellen wird. Um dieses Problem zu beheben, Sie also einfach die beiden Entfernen zusätzlicher NULL-Parameter, um den Draw-Aufruf.

```Output
\oclient\mainview.cpp(273) : error C2065: 'OLE_MAXNAMESIZE' : undeclared identifier
\oclient\mainview.cpp(273) : error C2057: expected constant expression
\oclient\mainview.cpp(280) : error C2664: 'CreateLinkFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '
\oclient\mainview.cpp(286) : error C2664: 'CreateFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '
\oclient\mainview.cpp(288) : error C2664: 'CreateStaticFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '
```

Die Fehler über das Ergebnis von der Tatsache ab, die alle die `COleClientItem::CreateXXXX` Funktionen in MFC/OLE1 erforderlich, dass ein eindeutiger Name übergeben werden, um das Element darstellt. Dies war eine Voraussetzung für die zugrunde liegenden OLE-API. Dies ist nicht in MFC/OLE 2 erforderlich, da es sich bei OLE 2 nicht DDE als der zugrunde liegende Mechanismus für die Kommunikation verwendet (der Name wurde im DDE-Konversationen verwendet). Um dieses Problem zu beheben, entfernen Sie die `CreateNewName` Funktion sowie alle Verweise darauf. Es ist einfach, um herauszufinden, was in dieser Version jeder MFC/OLE-Funktion erwartet wird, indem Sie einfach den Cursor auf den Aufruf zu platzieren und F1 drücken.

Ein weiterer Bereich, der deutlich unterscheidet ist die Behandlung von OLE 2-Zwischenablage. Mit OLE1 haben Sie die Windows-Zwischenablage APIs Interaktion mit der Zwischenablage verwendet. Mit OLE 2 erfolgt dies mit einem anderen Mechanismus. Die MFC/OLE1-APIs davon ausgegangen, dass die Zwischenablage geöffnet, vor dem Kopieren war einer `COleClientItem` Objekt in die Zwischenablage. Dies ist nicht mehr erforderlich und bewirkt, dass alle MFC/OLE-Zwischenablage-Vorgänge fehlschlagen. Während Sie den Code zum Entfernen von Abhängigkeiten in bearbeiten `CreateNewName`, sollten Sie auch den Code, der öffnet und schließt die Windows-Zwischenablage entfernen.

```Output
\oclient\mainview.cpp(332) : error C2065: 'AfxOleInsertDialog' : undeclared identifier
\oclient\mainview.cpp(332) : error C2064: term does not evaluate to a function
\oclient\mainview.cpp(344) : error C2057: expected constant expression
\oclient\mainview.cpp(347) : error C2039: 'CreateNewObject' : is not a member of 'CRectItem'
```

Diese Fehler entstehen die `CMainView::OnInsertObject` Handler. Behandeln des Befehls "Neues Objekt einfügen" ist ein weiterer Bereich, in denen Dinge ein wenig geändert haben. In diesem Fall ist es am einfachsten, einfach Zusammenführen von der ursprünglichen Implementierung, die von AppWizard für eine neue OLE Container-Anwendung bereitgestellt werden. In der Tat ist dies eine Technik, die Sie zum Portieren von anderen Anwendungen anwenden können. In MFC/OLE1, Sie im Dialogfeld "Objekt einfügen" angezeigt, durch den Aufruf `AfxOleInsertDialog` Funktion. In dieser Version, die Sie erstellen eine `COleInsertObject` Dialogfeldobjekt, und rufen `DoModal`. Darüber hinaus werden neue OLE-Elementen erstellt, mit einem **CLSID** anstelle einer Zeichenfolge Klassenname. Das Ergebnis sollte etwa wie folgt aussehen:

```cpp
COleInsertDialog dlg;
if (dlg.DoModal() != IDOK)
    return;

BeginWaitCursor();

CRectItem* pItem = NULL;
TRY
{
    // First create the C++ object
    pItem = GetDocument()->CreateItem();
    ASSERT_VALID(pItem);

    // Initialize the item from the dialog data.
    if (!dlg.CreateItem(pItem))
        AfxThrowMemoryException();
            // any exception will do
    ASSERT_VALID(pItem);

    // run the object if appropriate
    if (dlg.GetSelectionType() == COleInsertDialog::createNewItem)
        pItem->DoVerb(OLEIVERB_SHOW, this);

    // update right away
    pItem->UpdateLink();
    pItem->UpdateItemRectFromServer();

    // set selection to newly inserted item
    SetSelection(pItem);
    pItem->Invalidate();
}
CATCH (CException, e)
{
    // clean up item
    if (pItem != NULL)
        GetDocument()->DeleteItem(pItem);

    AfxMessageBox(IDP_FAILED_TO_CREATE);
}
END_CATCH

EndWaitCursor();
```

> [!NOTE]
> Neues Objekt einfügen kann für Ihre Anwendung anders sein):

Es ist auch erforderlich, Sie enthalten \<afxodlgs.h >, enthält die Deklaration für die `COleInsertObject` Dialogfeldklasse als auch das andere von MFC bereitgestellten Standarddialogfelder.

```Output
\oclient\mainview.cpp(367) : error C2065: 'OLEVERB_PRIMARY' : undeclared identifier
\oclient\mainview.cpp(367) : error C2660: 'DoVerb' : function does not take 1 parameters
```

Diese Fehler entstehen durch die Tatsache, die einige OLE1-Konstanten in OLE 2 geändert haben, obwohl das Konzept sie gleich sind. In diesem Fall `OLEVERB_PRIMARY` hat sich geändert, um `OLEIVERB_PRIMARY`. OLE1 sowohl OLE 2, in das primäre Verb in der Regel von einem Container ausgeführt, wenn der Benutzer auf ein Element doppelklickt.

Darüber hinaus `DoVerb` akzeptiert jetzt einen zusätzlichen Parameter, ein Zeiger auf eine Ansicht (`CView`*). Dieser Parameter wird nur verwendet, um "Visuelle Bearbeitung" (oder direkte Aktivierung) zu implementieren. Vorerst Sie diesen Parameter auf NULL gesetzt, da Sie dieses Feature zu diesem Zeitpunkt nicht implementiert werden.

Um sicherzustellen, dass das Framework nie versucht, ein direktes aktivieren, sollten Sie überschreiben `COleClientItem::CanActivate` wie folgt:

```cpp
BOOL CRectItem::CanActivate()
{
    return FALSE;
}
```

```Output
\oclient\rectitem.cpp(53) : error C2065: 'GetBounds' : undeclared identifier
\oclient\rectitem.cpp(53) : error C2064: term does not evaluate to a function
\oclient\rectitem.cpp(84) : error C2065: 'SetBounds' : undeclared identifier
\oclient\rectitem.cpp(84) : error C2064: term does not evaluate to a function
```

In MFC/OLE1 `COleClientItem::GetBounds` und `SetBounds` verwendet wurden, um Abfragen und bearbeiten das Ausmaß eines Elements (die `left` und `top` Mitglieder sind immer 0 (null)). In MFC/OLE 2 Dies wird direkt vom unterstützt `COleClientItem::GetExtent` und `SetExtent`, dem Umgang mit einem **Größe** oder `CSize` stattdessen.

Der Code für Ihre neue SetItemRectToServer, und UpdateItemRectFromServer Aufrufe wie folgt aussehen:

```cpp
BOOL CRectItem::UpdateItemRectFromServer()
{
    ASSERT(m_bTrackServerSize);
    CSize size;
    if (!GetExtent(&size))
        return FALSE;    // blank

    // map from HIMETRIC to screen coordinates
    {
        CClientDC screenDC(NULL);
        screenDC.SetMapMode(MM_HIMETRIC);
        screenDC.LPtoDP(&size);
    }
    // just set the item size
    if (m_rect.Size() != size)
    {
        // invalidate the old size/position
        Invalidate();
        m_rect.right = m_rect.left + size.cx;
        m_rect.bottom = m_rect.top + size.cy;
        // as well as the new size/position
        Invalidate();
    }
    return TRUE;
}

BOOL CRectItem::SetItemRectToServer()
{
    // set the official bounds for the embedded item
    CSize size = m_rect.Size();
    {
        CClientDC screenDC(NULL);
        screenDC.SetMapMode(MM_HIMETRIC);
        screenDC.DPtoLP(&size);
    }
    TRY
    {
        SetExtent(size);    // may do a wait
    }
    CATCH(CException, e)
    {
        return FALSE;  // links will not allow SetBounds
    }
    END_CATCH
    return TRUE;
}
```

```Output
\oclient\frame.cpp(50) : error C2039: 'InWaitForRelease' : is not a member of 'COleClientItem'
\oclient\frame.cpp(50) : error C2065: 'InWaitForRelease' : undeclared identifier
\oclient\frame.cpp(50) : error C2064: term does not evaluate to a function
```

In MFC/OLE1 synchrone API Aufrufen aus einem Container für einen Server waren *simulierten*, da OLE1 inhärent asynchron in vielen Fällen wurde. Es war erforderlich, vor der Verarbeitung von Befehlen, die vom Benutzer für einen ausstehenden asynchronen Aufruf in Bearbeitung zu überprüfen. MFC/OLE1-bereitgestellten der `COleClientItem::InWaitForRelease` -Funktion für die auf diese Weise. In MFC/OLE 2 ist dies nicht erforderlich, daher Sie um die Außerkraftsetzung der OnCommand in CMainFrame ganz zu entfernen können.

An diesem Punkt wird OCLIENT kompilieren und verknüpfen.

## <a name="other-necessary-changes"></a>Andere erforderlichen Änderungen

Es gibt einige Dinge, die nicht durchgeführt werden, die OCLIENT ausgeführt werden, jedoch erhalten bleiben. Es empfiehlt sich zum Beheben dieser Probleme anstelle des weiter unten.

Zunächst ist es erforderlich, um die OLE-Bibliotheken zu initialisieren. Dies erfolgt durch Aufrufen von `AfxOleInit` aus `InitInstance`:

```cpp
if (!AfxOleInit())
{
    AfxMessageBox("Failed to initialize OLE libraries");
    return FALSE;
}
```

Es ist auch eine gute Idee, überprüfen Sie für die virtuellen Funktionen für Parameter geändert wird. Eine solche Funktion ist `COleClientItem::OnChange`, außer Kraft gesetzte in jeder MFC/OLE-Container-Anwendung. Betrachten Sie Onlinehilfe, sehen Sie sich, dass eine zusätzliche "DWORD DwParam hinzugefügt wurde. Die neue CRectItem::OnChange sieht wie folgt aus:

```cpp
void
CRectItem::OnChange(OLE_NOTIFICATION wNotification, DWORD dwParam)
{
    if (m_bTrackServerSize && !UpdateItemRectFromServer())
    {
        // Blank object
        if (wNotification == OLE_CLOSED)
        {
            // no data received for the object - destroy it
            ASSERT(!IsVisible());
            GetDocument()->DeleteItem(this);
            return; // no update (item is gone now)
        }
    }
    if (wNotification != OLE_CLOSED)
        Dirty();
    Invalidate();
    // any change will cause a redraw
}
```

In MFC/OLE1, abgeleiteten containeranwendungen Document-Klasse aus `COleClientDoc`. In MFC/OLE 2 diese Klasse wurde entfernt und ersetzt durch `COleDocument` (diese neue Organisation erleichtert es, erstellen Sie Container/Server-Anwendungen). Gibt es eine **#define** zugeordnet `COleClientDoc` zu `COleDocument` zur Vereinfachung der Portierung von MFC/OLE1-Anwendungen zu MFC/OLE 2, wie z. B. OCLIENT. Eines der Features, die nicht vom `COleDocument` , bereitgestellt wurde, indem `COleClientDoc` ist die standard-Befehlsnachricht Zuordnungseinträgen. Dies geschieht dies, serveranwendungen, die ebenfalls verwenden `COleDocument` (indirekt), leiten keine mit ihnen den Aufwand für diese Befehlshandler, wenn sie einen Container/Server-Anwendung sind. Sie müssen die folgenden Einträge hinzufügen, um die meldungszuordnung CMainDoc:

```cpp
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE, OnUpdatePasteMenu)
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE_LINK, OnUpdatePasteLinkMenu)
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_LINKS, OnUpdateEditLinksMenu)
ON_COMMAND(ID_OLE_EDIT_LINKS, COleDocument::OnEditLinks)
ON_UPDATE_COMMAND_UI(ID_OLE_VERB_FIRST, OnUpdateObjectVerbMenu)
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_CONVERT, OnUpdateObjectVerbMenu)
ON_COMMAND(ID_OLE_EDIT_CONVERT, OnEditConvert)
```

Die Implementierung dieser Befehle wird `COleDocument`, dies ist die Basisklasse für Ihr Dokument.

An diesem Punkt ist OCLIENT eine funktionale OLE-Container-Anwendung. Es ist möglich, die Elemente eines beliebigen Typs (OLE1 oder OLE 2) einfügen. Da es sich bei der erforderlichen Code für ein direktes-Aktivierung nicht implementiert wird, werden Elemente in einem separaten Fenster ähnlich wie mit OLE1 bearbeitet. Im nächste Abschnitt erläutert die erforderlichen Änderungen aus, um direkte Bearbeitung (manchmal als "Visuelle Bearbeitung" bezeichnet) zu aktivieren.

## <a name="adding-visual-editing"></a>Hinzufügen von "Visuelle Bearbeitung"

Eines der interessantesten Features von OLE ist die direkte Aktivierung (oder "Visuelle Bearbeitung"). Dieses Feature ermöglicht die Serveranwendung aus, übernehmen Sie Teile des Containers-Benutzeroberfläche eine nahtlose bearbeitende-Schnittstelle für den Benutzer bereitgestellt. Um OCLIENT direkte Aktivierung implementieren zu können, müssen einige besonderen Ressourcen sowie zusätzlicher Code hinzugefügt werden. Diese Ressourcen und den Code werden normalerweise von AppWizard bereitgestellt, in der Tat Großteil des Codes hier direkt aus einer neuen AppWizard-Anwendung mit Unterstützung für "Container" übernommen wurde.

Zunächst einmal ist es erforderlich, fügen eine Menüressource verwendet werden, wenn es ist ein Element, das direkt aktiv ist. Sie können diese zusätzlichen Menüressourcen in Visual C++ erstellen, durch Kopieren der IDR_OCLITYPE-Ressource, und entfernen alle bis auf die Datei und Fenster-Popups. Zwei Trennlinien zwischen der Datei und Fenster-Popups an, dass die Trennung von Gruppen eingefügt (es sollte wie folgt aussehen: Datei &#124; &#124; Fenster). Weitere Informationen zur Bedeutung dieser Trennzeichen und wie der Server und-Container Menüs zusammengeführt werden finden Sie unter [Menüs und Ressourcen: Das Zusammenführen von Menüs](../mfc/menus-and-resources-menu-merging.md).

Nachdem Sie diese Menüs erstellt haben, müssen Sie das Framework, die ihnen bekannten Informationen zu informieren. Dies erfolgt durch Aufrufen von `CDocTemplate::SetContainerInfo` für die Dokumentvorlage, bevor Sie ihn der Dokument-Vorlagenliste in InitInstance hinzufügen. Der neue Code zum Registrieren der Dokumentvorlage sieht folgendermaßen aus:

```cpp
CDocTemplate* pTemplate = new CMultiDocTemplate(
    IDR_OLECLITYPE,
    RUNTIME_CLASS(CMainDoc),
    RUNTIME_CLASS(CMDIChildWnd), // standard MDI child frame
    RUNTIME_CLASS(CMainView));

pTemplate->SetContainerInfo(IDR_OLECLITYPE_INPLACE);

AddDocTemplate(pTemplate);
```

Die Ressource IDR_OLECLITYPE_INPLACE ist die spezielle direktes-Ressource, die in Visual C++ erstellt.

Um die direkte Aktivierung zu ermöglichen, sind einige Faktoren, die in beiden ändern, müssen die `CView` (CMainView) abgeleitete Klasse als auch die `COleClientItem` abgeleitete Klasse (CRectItem). Alle diese Außerkraftsetzungen von AppWizard bereitgestellt werden, und den größten Teil der Implementierung direkt über eine standardanwendung von AppWizard stammen.

Im ersten Schritt dieses Ports, direkte Aktivierung deaktiviert wurde, vollständig durch Überschreiben `COleClientItem::CanActivate`. Diese Überschreibung muss entfernt werden, um direkte Aktivierung zu ermöglichen. Darüber hinaus wurde NULL übergeben, um alle Aufrufe von `DoVerb` (es gibt zwei davon vorhanden), da die Ansicht bereitstellen nur für die direkte Aktivierung notwendig war. Um die direkte Aktivierung vollständig zu implementieren, ist es erforderlich, übergeben Sie die richtige Ansicht in der `DoVerb` aufrufen. Eine dieser Aufrufe ist `CMainView::OnInsertObject`:

```cpp
pItem->DoVerb(OLEIVERB_SHOW, this);
```

Ein weiteres Beispiel ist `CMainView::OnLButtonDblClk`:

```cpp
m_pSelection->DoVerb(OLEIVERB_PRIMARY, this);
```

Es ist erforderlich, außer Kraft setzen `COleClientItem::OnGetItemPosition`. Dies weist den Server, wo Sie das Fenster relativ zum Fenster für den Container eingefügt werden, wenn das Element direkt aktiviert wird. Für OCLIENT ist die Implementierung einfach:

```cpp
void CRectItem::OnGetItemPosition(CRect& rPosition)
{
    rPosition = m_rect;
}
```

Die meisten Server implementieren auch zuerst eine so genannte "Direktes Ändern der Größe." Dadurch wird das Fenster "Server" die Größe und verschoben, während der Benutzer das Element bearbeitet werden. Diese Aktion muss der Container teilnehmen, da verschieben oder Ändern der Größe des Fensters wird in der Regel die Position und Größe innerhalb des Containerdokuments selbst wirkt sich auf. Die Implementierung für OCLIENT synchronisiert die internen Rechteck, das vom M_rect mit der neuen Position und Größe verwaltet werden.

```cpp
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

An diesem Punkt ist genug Code zu einem Element, das direkt aktiviert werden und zum Umgang mit größenanpassung und verschieben das Element aus, wenn er aktiv ist vorhanden, aber kein Code kann der Benutzer die bearbeitungssitzung zu schließen. Einige Server diese Funktion selbst bieten eine werden durch die ESC-Taste verarbeiten, wird empfohlen, dass Container geben Sie zwei Möglichkeiten, um ein Element zu deaktivieren: (1) Sie können Sie durch Klicken auf außerhalb des Elements, und (2) die ESC-Taste drücken.

Hinzufügen einer Zugriffstaste mit Visual C++, der die Taste "VK_ESCAPE" zu einem Befehl zugeordnet, ID_CANCEL_EDIT wird hinzugefügt, auf die Ressourcen, für die ESC-Taste. Der Handler für diesen Befehl die folgende:

```cpp
// The following command handler provides the standard
// keyboard user interface to cancel an in-place
// editing session.void CMainView::OnCancelEdit()
{
    // Close any in-place active item on this view.
    COleClientItem* pActiveItem =
        GetDocument()->GetInPlaceActiveItem(this);
    if (pActiveItem != NULL)
        pActiveItem->Close();
    ASSERT(GetDocument()->GetInPlaceActiveItem(this) == NULL);
}
```

Um Fälle zu behandeln, in denen der Benutzer, außerhalb des Elements klickt, fügen Sie den folgenden Code am Anfang des `CMainView::SetSelection`:

```cpp
if (pNewSel != m_pSelection || pNewSel == NULL)
{
    COleClientItem* pActiveItem =
        GetDocument()->GetInPlaceActiveItem(this);
    if (pActiveItem != NULL&& pActiveItem != pNewSel)
        pActiveItem->Close();
}
```

Wenn ein Element direkt aktiv ist, sollte es den Fokus besitzt. Um sicherzustellen, dass dies der Fall ist verarbeiten Sie OnSetFocus, damit Sie den Fokus immer an das aktive Element übertragen wird, wenn Ihrer Ansicht den Fokus erhält:

```cpp
// Special handling of OnSetFocus and OnSize are required
// when an object is being edited in-place.
void CMainView::OnSetFocus(CWnd* pOldWnd)
{
    COleClientItem* pActiveItem =
        GetDocument()->GetInPlaceActiveItem(this);

    if (pActiveItem != NULL &&
        pActiveItem->GetItemState() == COleClientItem::activeUIState)
    {
        // need to set focus to this item if it is same view
        CWnd* pWnd = pActiveItem->GetInPlaceWindow();
        if (pWnd != NULL)
        {
            pWnd->SetFocus();   // don't call the base class
            return;
        }
    }

    CView::OnSetFocus(pOldWnd);
}
```

Wenn die Ansicht geändert wird, müssen Sie das aktive Element zu benachrichtigen, das dass das Clippingrechteck geändert hat. Zu diesem Zweck geben Sie einen Handler für `OnSize`:

```cpp
void CMainView::OnSize(UINT nType, int cx, int cy)
{
    CView::OnSize(nType, cx, cy);
    COleClientItem* pActiveItem =
        GetDocument()->GetInPlaceActiveItem(this);
    if (pActiveItem != NULL)
        pActiveItem->SetItemRects();
}
```

## <a name="case-study-hiersvr-from-mfc-20"></a>Fallstudie: HIERSVR von MFC 2.0

[HIERSVR](../overview/visual-cpp-samples.md) wurde auch in MFC 2.0 und OLE mit MFC/OLE1 implementiert. Dieser Hinweis beschreibt kurz die Schritte, die mit denen diese Anwendung anfänglich konvertiert wurde, um die Klassen von MFC/OLE 2 verwenden. Eine Reihe von Funktionen wurden hinzugefügt, nachdem der erste Port abgeschlossen wurde, um die Klassen von MFC/OLE 2 besser zu veranschaulichen. Diese Funktionen werden hier nicht behandelt; Das Beispiel selbst, um mehr über die erweiterten Features finden Sie unter.

> [!NOTE]
> Die c#-Compilerfehlern und schrittweise Anleitungen wurde mit Visual C++-2.0 erstellt. Fehlermeldungen und Speicherorte können mit Visual C++ 4.0 geändert haben, aber bleibt gültig, die konzeptionelle Informationen.

## <a name="getting-it-up-and-running"></a>Es einrichten und ausführen

Ansatz wird so portieren Sie das Beispiel HIERSVR zu MFC/OLE wird durch die Erstellung und Beheben der offensichtlichen Compilerfehler, die sich ergeben, werden gestartet. Wenn Sie verwenden Sie die HIERSVR von MFC 2.0 und kompilieren es unter dieser Version von MFC, finden Sie, dass es nicht viele Fehler zu beheben (obwohl es mehr als mit dem OCLIENT-Beispiel sind). Die Fehler in der Reihenfolge, in der sie in der Regel auftreten, werden nachfolgend beschrieben.

## <a name="compile-and-fix-errors"></a>Kompilieren und Beheben von Fehlern

```Output
\hiersvr\hiersvr.cpp(83) : error C2039: 'RunEmbedded' : is not a member of 'COleTemplateServer'
```

Diese erste Fehler zeigt an, eine viel größere Problem mit der `InitInstance` -Funktion für den Server. Die Initialisierung für einen OLE-Server erforderlich sind, ist wahrscheinlich eine der größten Änderungen, die Sie an Ihrer Anwendung MFC/OLE1 abzurufenden ausführen vornehmen müssen. Die beste Vorgehensweise ist, was AppWizard erstellt, die sich für einen OLE-Server anzeigen und ändern den Code entsprechend. Hier sind einige Punkte zu beachten:

Es ist erforderlich, die OLE-Bibliotheken zu initialisieren, indem aufrufen `AfxOleInit`

Rufen Sie SetServerInfo für Dokumentvorlagenobjekt Ressource verarbeitet und Laufzeit-Klasseninformationen, die Sie mit nicht festlegen können die `CDocTemplate` Konstruktor.

Das Hauptfenster der Anwendung nicht angezeigt werden, wenn/Embedding vorhanden, in der Befehlszeile angegeben ist.

Sie müssen eine **GUID** für Ihr Dokument. Dies ist ein eindeutiger Bezeichner für den Dokumenttyp (128 Bit). AppWizard erstellt für Sie – Wenn Sie hier die beschriebene Technik verwenden, kopieren Sie den neuen Code aus einer neuen Serveranwendung von AppWizard generiert, Sie können einfach "stehlen" die GUID aus der Anwendung. Falls dies nicht der Fall ist, können Sie die GUIDGEN. EXE-Hilfsprogramm im BIN-Verzeichnis.

Es ist erforderlich, die "connect" Ihre `COleTemplateServer` Objekt, das die Dokumentvorlage durch Aufrufen von `COleTemplateServer::ConnectTemplate`.

Aktualisieren Sie die Registrierung des Systems, wenn Ihre Anwendung als eigenständige ausgeführt wird. Wenn der Benutzer auf diese Weise die. EXE-Datei für Ihre Anwendung, über den neuen Speicherort ausführen die Windows-System-Registrierungsdatenbank, zeigen Sie auf den neuen Speicherort aktualisiert.

Nach dem Anwenden aller dieser ändert sich basierend auf was AppWizard erstellt `InitInstance`, `InitInstance` (und verwandte GUID) für HIERSVR sollte wie folgt aussehen:

```cpp
// this is the GUID for HIERSVR documents
static const GUID BASED_CODE clsid =
{ 0xA0A16360L, 0xC19B, 0x101A, { 0x8C, 0xE5, 0x00, 0xDD, 0x01, 0x11, 0x3F, 0x12 } };

/////////////////////////////////////////////////////////////////////////////
// COLEServerApp initialization

BOOL COLEServerApp::InitInstance()
{
    // OLE 2 initialization
    if (!AfxOleInit())
    {
        AfxMessageBox("Initialization of the OLE failed!");
        return FALSE;
    }

    // Standard initialization
    LoadStdProfileSettings();   // Load standard INI file options

    // Register document templates
    CDocTemplate* pDocTemplate;
    pDocTemplate = new CMultiDocTemplate(IDR_HIERSVRTYPE,
        RUNTIME_CLASS(CServerDoc),
        RUNTIME_CLASS(CMDIChildWnd),
        RUNTIME_CLASS(CServerView));
    pDocTemplate->SetServerInfo(IDR_HIERSVRTYPE_SRVR_EMB);
    AddDocTemplate(pDocTemplate);

    // create main MDI Frame window
    CMainFrame* pMainFrame = new CMainFrame;
    if (!pMainFrame->LoadFrame(IDR_MAINFRAME))
        return FALSE;
    m_pMainWnd = pMainFrame;

    SetDialogBkColor(); // gray look

    // enable file manager drag/drop and DDE Execute open
    m_pMainWnd->DragAcceptFiles();
    EnableShellOpen();

    m_server.ConnectTemplate(clsid, pDocTemplate, FALSE);
    COleTemplateServer::RegisterAll();

    // try to launch as an OLE server
    if (RunEmbedded())
    {
        // "short-circuit" initialization -- run as server!
        return TRUE;
    }
    m_server.UpdateRegistry();
    RegisterShellFileTypes();

    // not run as OLE server, so show the main window
    if (m_lpCmdLine[0] == '\0')
    {
        // create a new (empty) document
        OnFileNew();
    }
    else
    {
        // open an existing document
        OpenDocumentFile(m_lpCmdLine);
    }

    pMainFrame->ShowWindow(m_nCmdShow);
    pMainFrame->UpdateWindow();

    return TRUE;
}
```

Beachten Sie, dass der obige Code auf eine neue Ressourcen-ID, IDR_HIERSVRTYPE_SRVR_EMB bezieht. Dies ist die Menüressource verwendet werden, wenn ein Dokument, das in einen anderen Container eingebettete bearbeitet wird. In MFC/OLE1 wurden die Menüelemente, die spezifisch für ein eingebettetes Element bearbeiten dynamisch geändert. Verwenden eine ganz anderes Menüstruktur beim Bearbeiten der eines eingebetteten Elements anstelle von dateibasierten Dokument bearbeiten erleichtert diese zwei Modi unterschiedliche Benutzeroberflächen bereit. Wie Sie später sehen werden, wird eine völlig separate Menüressource verwendet, wenn Sie ein eingebettetes Objekt direkt bearbeiten.

Um diese Ressource zu erstellen, laden Sie das Ressourcenskript in Visual C++, und kopieren Sie die vorhandene IDR_HIERSVRTYPE Menüressource aus. Benennen Sie die neue Ressource zu IDR_HIERSVRTYPE_SRVR_EMB (Hierbei handelt es sich um dieselben Namenskonventionen gelten, die von AppWizard verwendet). Als Nächstes ändern Sie "Datei speichern" in "Aktualisieren der Datei"; Geben Sie ihm ID ID_FILE_UPDATE-Befehl. Ändern Sie außerdem "Datei speichern unter" auf "Datei Kopie speichern unter"; Geben Sie ihm ID ID_FILE_SAVE_COPY_AS-Befehl. Das Framework bietet die Implementierung der beiden folgenden Befehle.

```Output
\hiersvr\svritem.h(60) : error C2433: 'OLESTATUS' : 'virtual' not permitted on data declarations
\hiersvr\svritem.h(60) : error C2501: 'OLESTATUS' : missing decl-specifiers
\hiersvr\svritem.h(60) : error C2146: syntax error : missing ';' before identifier 'OnSetData'
\hiersvr\svritem.h(60) : error C2061: syntax error : identifier 'OLECLIPFORMAT'
\hiersvr\svritem.h(60) : error C2501: 'OnSetData' : missing decl-specifiers
```

Es gibt eine Reihe von Fehlern, die durch die Außerkraftsetzung der `OnSetData`, da er verweist die **OLESTATUS** Typ. **OLESTATUS** war die Möglichkeit, OLE1 Fehler zurückgegebenen. Dies wurde geändert, um **HRESULT** in OLE 2, obwohl MFC in der Regel konvertiert einen **HRESULT** in einer `COleException` mit dem Fehler. In diesem Fall die Überschreibung der `OnSetData` ist nicht mehr erforderlich, damit die einfachste Möglichkeit ist, um ihn zu entfernen.

```Output
\hiersvr\svritem.cpp(30) : error C2660: 'COleServerItem::COleServerItem' : function does not take 1 parameters
```

Die `COleServerItem` Konstruktor akzeptiert einen zusätzlichen Parameter für "BOOL". Dieses Flag gibt an, wie die Verwaltung des Arbeitsspeichers auf erfolgt die `COleServerItem` Objekte. Durch Festlegung auf "true", das Framework die Speicherverwaltung dieser Objekte verarbeitet, sie zu löschen, wenn sie nicht mehr benötigt werden. HIERSVR verwendet `CServerItem` (abgeleitet von `COleServerItem`) Objekte, die als Teil seiner eigenen Daten, damit Sie dieses Flag auf "false" festlegen. Dadurch können HIERSVR zu bestimmen, wenn jedes Serverelement gelöscht wird.

```Output
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class
```

Wie diese Fehler bereits andeuten, gibt es einige 'rein virtuell'-Funktionen, die nicht in CServerItem überschrieben wurden. In den meisten Fällen wird dies durch die Tatsache verursacht, die OnDraws-Parameterliste geändert wurde. Um diesen Fehler zu beheben, ändern `CServerItem::OnDraw` (sowie der Deklaration in svritem.h) wie folgt:

```cpp
BOOL CServerItem::OnDraw(CDC* pDC, CSize& rSize)
{
    // request from OLE to draw node
    pDC->SetMapMode(MM_TEXT); // always in pixels
    return DoDraw(pDC, CPoint(0, 0), FALSE);
}
```

Der neue Parameter heißt "rSize". Dadurch können Sie in der der Zeichnung ausgefüllt, wenn praktische. Diese Größe muss sich im **HIMETRIC**. In diesem Fall es ist nicht praktisch, geben Sie diesen Wert, damit das Framework ruft `OnGetExtent` zum Abrufen des Wertebereichs. Damit dies funktioniert, müssen Sie zum Implementieren `OnGetExtent`:

```cpp
BOOL CServerItem::OnGetExtent(DVASPECT dwDrawAspect, CSize& rSize)
{
    if (dwDrawAspect != DVASPECT_CONTENT)
        return COleServerItem::OnGetExtent(dwDrawAspect, rSize);

    rSize = CalcNodeSize();
    return TRUE;
}
```

```Output
\hiersvr\svritem.cpp(104) : error C2065: 'm_rectBounds' : undeclared identifier
\hiersvr\svritem.cpp(104) : error C2228: left of '.SetRect' must have class/struct/union type
\hiersvr\svritem.cpp(106) : error C2664: 'void __pascal __far DPtoLP(struct ::tagPOINT __far *,
    int)__far const ' : cannot convert parameter 1 from 'int __far *' to 'struct ::tagPOINT __far *'
```

In der CServerItem::CalcNodeSize-Funktion wird in die Elementgröße konvertiert **HIMETRIC** und in gespeichert *M_rectBounds*. Die nicht dokumentierte "*M_rectBounds*" Mitglied `COleServerItem` ist nicht vorhanden (es wurde teilweise durch ersetzt *M_sizeExtent*, aber in OLE 2 hat dieser Member eine etwas andere Verwendung als *M_rectBounds* in OLE1 haben). Statt die **HIMETRIC** Größe in diese Membervariable wird es zurückgegeben. Dieser Rückgabewert wird verwendet, `OnGetExtent`, die bereits implementiert.

```cpp
CSize CServerItem::CalcNodeSize()
{
    CClientDC dcScreen(NULL);

    m_sizeNode = dcScreen.GetTextExtent(m_strDescription,
        m_strDescription.GetLength());
    m_sizeNode += CSize(CX_INSET * 2, CY_INSET * 2);

    // set suggested HIMETRIC size
    CSize size(m_sizeNode.cx, m_sizeNode.cy);
    dcScreen.SetMapMode(MM_HIMETRIC);
    dcScreen.DPtoLP(&size);
    return size;
}
```

CServerItem überschreibt auch `COleServerItem::OnGetTextData`. Diese Funktion ist in MFC/OLE veraltet und wird durch einen anderen Mechanismus ersetzt. Die MFC 3.0-Version von MFC-OLE-Beispiel [HIERSVR](../overview/visual-cpp-samples.md) implementiert diese Funktionalität durch Überschreiben der `COleServerItem::OnRenderFileData`. Diese Funktionalität ist nicht wichtig, dass dieser einfache Port, damit Sie die Außerkraftsetzung OnGetTextData entfernen können.

Es gibt viele weitere Fehler in svritem.cpp, die nicht behandelt wurden. Sie sind nicht "echten" Fehler: nur Fehler, die durch vorherige Fehler verursacht.

```Output
\hiersvr\svrview.cpp(325) : error C2660: 'CopyToClipboard' : function does not take 2 parameters
```

`COleServerItem::CopyToClipboard` unterstützt nicht mehr die `bIncludeNative` Flag. Die systemeigenen Daten (die Daten geschrieben, indem das Serverelement Serialize-Funktion) ist immer kopiert, sodass Sie den ersten Parameter zu entfernen. Darüber hinaus `CopyToClipboard` wird eine Ausnahme ausgelöst, wenn ein Fehler tritt auf, anstatt von "false". Ändern Sie den Code für CServerView::OnEditCopy wie folgt:

```cpp
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

Zwar gab es weitere aufgetretene Fehler bei der Kompilierung die MFC-2.0-Version des HIERSVR als für die gleiche Version von OCLIENT vorhanden waren, gab es tatsächlich weniger Änderungen.

An diesem Punkt HIERSVR kompiliert und verknüpft und fungieren als OLE-Server, aber ohne die Bearbeitung direktes-Funktion, die als Nächstes implementiert wird.

## <a name="adding-visual-editing"></a>Hinzufügen von "Visuelle Bearbeitung"

Um diese Server-Anwendung "Visuelle Bearbeitung" (oder direkte Aktivierung) hinzuzufügen, gibt es nur ein paar Dinge, die, denen Sie erledigen müssen:

- Sie benötigen eine spezielle Menüressource verwendet werden, wenn das Element direkt aktiv ist.

- Diese Anwendung hat eine Symbolleiste, daher Sie eine Symbolleiste mit nur ein Teil der normal-Symbolleiste benötigen entsprechend die Befehle im Menü auf dem Server verfügbar (mit der oben genannte Menüressource übereinstimmt).

- Sie benötigen eine neue Klasse abgeleitet `COleIPFrameWnd` , die direkte Benutzeroberfläche bereitstellt (ähnlich wie bei CMainFrame, abgeleitet `CMDIFrameWnd`, die MDI Benutzeroberfläche bereit).

- Sie müssen das Framework über diese speziellen Ressourcen und Klassen zu informieren.

Die Menüressource ist einfach zu erstellen. Führen Sie Visual C++, kopieren Sie die Menüressource IDR_HIERSVRTYPE in einer Menüressource IDR_HIERSVRTYPE_SRVR_IP aufgerufen. Ändern Sie im Menü aus, sodass nur für die Verwendung der Bearbeiten und die Hilfe im Menü Popups bleiben. Hinzufügen von zwei Trennzeichen zum Menü zwischen der Menüs bearbeiten und Hilfe (es sollte wie folgt aussehen: Bearbeiten Sie &#124; &#124; unterstützen). Weitere Informationen zu der Bedeutung dieser Trennzeichen und wie der Server und-Container Menüs zusammengeführt werden, finden Sie unter [Menüs und Ressourcen: Das Zusammenführen von Menüs](../mfc/menus-and-resources-menu-merging.md).

Die Bitmap für die Teilmenge-Symbolleiste kann problemlos erstellt werden, durch Kopieren das entsprechende Element aus einer neuen AppWizard generiert-Anwendung mit der Option "Server" aktiviert. Diese Bitmap kann dann in Visual C++ importiert werden. Achten Sie darauf, dass der Bitmap eine ID von IDR_HIERSVRTYPE_SRVR_IP gewähren.

Abgeleitete Klasse von `COleIPFrameWnd` können aus einer Anwendung generierten AppWizard mit Serversupport sowie kopiert werden. Kopieren Sie beide Dateien IPFRAME. CPP und IPFRAME. H und fügen sie dem Projekt hinzu. Stellen Sie sicher, dass die `LoadBitmap` Aufruf bezieht sich auf die IDR_HIERSVRTYPE_SRVR_IP, die Bitmap, die im vorherigen Schritt erstellt haben.

Nun, da alle neuen Ressourcen und Klassen erstellt werden, fügen Sie den erforderlichen Code, sodass das Framework diese kennt (und weiß, dass diese Anwendung jetzt direkte Bearbeitung unterstützt). Dies erfolgt durch einige weitere Parameter zum Hinzufügen der `SetServerInfo` rufen Sie in der `InitInstance` Funktion:

```cpp
pDocTemplate->SetServerInfo(IDR_HIERSVRTYPE_SRVR_EMB,
    IDR_HIERSVRTYPE_SRVR_IP,
    RUNTIME_CLASS(CInPlaceFrame));
```

Es ist jetzt bereit zur Ausführung des direktes in allen Containern, die auch die direkte Aktivierung unterstützt. Es wird jedoch eine geringfügige Fehler, die immer noch den Code sein. HIERSVR unterstützt ein Kontextmenü angezeigt, wenn der Benutzer mit die rechten Maustaste drückt. Dieses Menü funktioniert, wenn HIERSVR vollständig geöffnet ist, aber nicht funktioniert, wenn Sie eine einbettende direktes Editieren. Der Grund kann auf diese einzelne Codezeile in CServerView::OnRButtonDown festgesetzt werden:

```cpp
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,
    point.x,
    point.y,
    AfxGetApp()->m_pMainWnd);
```

Beachten Sie, dass den Verweis auf `AfxGetApp()->m_pMainWnd`. Wenn der Server direkt aktiviert ist, kann ein Hauptfenster und M_pMainWnd festgelegt ist, aber er ist in der Regel nicht sichtbar. Darüber hinaus bezieht sich in diesem Fenster auf die *main* Fenster der Anwendung, die MDI-Rahmenfenster, das angezeigt wird, wenn der Server vollständig ist öffnen oder eigenständig ausgeführt. Es verweist nicht auf das Fenster des aktiven Frames, die beim direkten aktiviert ist ein Frame Fenster abgeleitet `COleIPFrameWnd`. Um das richtige aktive Fenster zu erhalten, selbst wenn die direkte Bearbeitung, diese Version von MFC eine neue Funktion, fügt `AfxGetMainWnd`. Im Allgemeinen sollten Sie diese Funktion statt des verwenden `AfxGetApp()->m_pMainWnd`. Dieser Code muss wie folgt ändern:

```cpp
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,
    point.x,
    point.y,
    AfxGetMainWnd());
```

Sie haben jetzt einen OLE-Server, die mindestens für die funktionale direkte Aktivierung aktiviert. Es stehen jedoch noch viele Funktionen mit MFC/OLE 2, die nicht in MFC/OLE1 verfügbar waren. Finden Sie im Beispiel HIERSVR Weitere Ideen für Features, die Sie implementieren möchten. Einige der Features, die HIERSVR implementiert sind unten aufgeführt:

- Zoom für "true" WYSIWYG-Verhalten in Bezug auf den Container.

- Drag / drop- und ein benutzerdefinierter Zwischenablageformat.

- Durchführen eines Bildlaufs Containerfenster wie die Auswahl geändert wird.

Das Beispiel HIERSVR in MFC 3.0 verwendet auch einen etwas anderen Entwurf für die Serverelemente. Dadurch wird Speicherplatz gespart und Ihre Verknüpfungen flexibler. Mit Version 2.0 der HIERSVR jeder Knoten in der Struktur *ist-ein* `COleServerItem`. `COleServerItem` führt ein wenig mehr Aufwand als unbedingt erforderlich ist, für jeden dieser Knoten ist jedoch ein `COleServerItem` für jeden aktiven Link ist erforderlich. Aber zum größten Teil, es gibt sehr wenige aktive Links zu jedem Zeitpunkt. Um dies effizienter zu gestalten, trennt der HIERSVR in dieser Version von MFC den Knoten aus der `COleServerItem`. Es hat sowohl eine CServerNode und `CServerItem` Klasse. Die `CServerItem` (abgeleitet von `COleServerItem`) wird nur bei Bedarf erstellt. Nachdem der Container (oder Container) nicht mehr, verwenden diesen bestimmten Link zu diesem bestimmten Knoten, wird das CServerItem-Objekt, das die CServerNode zugeordneten gelöscht. Dieser Entwurf ist effizienter und flexibler. Die Flexibilität ist beim Umgang mit mehreren Auswahl. Keines der folgenden beiden Versionen der HIERSVR Mehrfachauswahl unterstützen, aber es wäre wesentlich einfacher, hinzufügen (und Links, um diese Auswahl unterstützen), mit der MFC-3.0-Version von HIERSVR, da die `COleServerItem` von systemeigenen Daten getrennt ist.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
