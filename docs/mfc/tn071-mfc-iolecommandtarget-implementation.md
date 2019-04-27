---
title: 'TN071: MFC-IOleCommandTarget-Implementierung'
ms.date: 06/28/2018
f1_keywords:
- IOleCommandTarget
helpviewer_keywords:
- TN071 [MFC]
- IOleCommandTarget interface [MFC]
ms.assetid: 3eef571e-6357-444d-adbb-6f734a0c3161
ms.openlocfilehash: dca1183a17fe8f3022f517d1ad0c3932ea272417
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167997"
---
# <a name="tn071-mfc-iolecommandtarget-implementation"></a>TN071: MFC-IOleCommandTarget-Implementierung

> [!NOTE]
> Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

Die `IOleCommandTarget` Schnittstelle ermöglicht, Objekte und deren Container aus, um Befehle miteinander zu senden. Z. B. eines Objekts Symbolleisten möglicherweise enthalten Sie Schaltflächen für Befehle wie z. B. `Print`, `Print Preview`, `Save`, `New`, und `Zoom`. Wenn ein solches Objekt eingebettet wurden, in einem Container, die unterstützt `IOleCommandTarget`, das Objekt konnte aktivieren Sie die Schaltflächen und die Befehle in den Container für die Verarbeitung, wenn der Benutzer geklickt, sie hat weiterleiten. Wenn ein Container das eingebettete Objekt selbst drucken möchten, können erleichtern diese Anforderung durch Senden eines Befehls über die `IOleCommandTarget` Schnittstelle des eingebetteten Objekts.

`IOleCommandTarget` ist Sie eine Automation-ähnliche Schnittstelle, da es von einem Client zum Aufrufen von Methoden auf einem Server verwendet wird. Jedoch `IOleCommandTarget` spart den Mehraufwand der Aufrufe über Automatisierungsschnittstellen, da keine Programmierer verwenden, die in der Regel aufwändige `Invoke` -Methode der `IDispatch`.

In MFC können die `IOleCommandTarget` Schnittstelle wird von Server für aktive Dokumente verwendet, können Active Document-Container, um Befehle an den Server zu senden. Das aktive Dokument Serverklasse `CDocObjectServerItem`, verwendet MFC-schnittstellenzuordnungen (finden Sie unter [tn038 Implementieren von: Implementierung von IUnknown MFC/OLE](../mfc/tn038-mfc-ole-iunknown-implementation.md)) zum Implementieren der `IOleCommandTarget` Schnittstelle.

`IOleCommandTarget` wird auch in implementiert die `COleFrameHook` Klasse. `COleFrameHook` ist eine nicht dokumentierte MFC-Klasse, die die Frame-Fenster-Funktionalität der direkten Bearbeitung Container implementiert. `COleFrameHook` verwendet auch die MFC-schnittstellenzuordnungen zum Implementieren der `IOleCommandTarget` Schnittstelle. `COleFrameHook`die Implementierung von `IOleCommandTarget` leitet der OLE-Befehle zum `COleDocObjectItem`-abgeleitete Active Document-Container. Dadurch können alle MFC Active Document-Container zum Empfangen von Nachrichten aus eigenständigen Active Document-Server.

## <a name="mfc-ole-command-maps"></a>MFC-OLE-Befehlszuordnungen

MFC-Entwickler nutzen `IOleCommandTarget` mithilfe von MFC-OLE Befehl Zuordnungen. OLE-befehlszuordnungen ähneln meldungszuordnungen, da sie verwendet werden können, um OLE-Befehle Memberfunktionen der Klasse zuzuordnen, die die Zuordnung der Befehl enthält. Damit dies funktioniert, platzieren Sie Makros in der Zuordnung Befehl an der der Befehl, die Sie behandeln möchten, die OLE-Befehl und die Befehls-ID der Befehlsgruppe OLE der [WM_COMMAND](/windows/desktop/menurc/wm-command) Nachricht, die gesendet wird, wenn der OLE-Befehl empfangen wird. MFC enthält außerdem eine Reihe von vordefinierten Makros für OLE-Standardbefehle. Eine Liste mit den standard-OLE-Befehle, die ursprünglich für entworfen wurden mit Microsoft Office-Anwendungen, finden Sie unter der OLECMDID-Enumeration, die in docobj.h definiert ist.

Wenn ein OLE-Befehl von einer MFC_Anwendung, die Zuordnung ein OLE-Befehl enthält empfangen wird, sucht MFC die Befehls-ID und die Befehlsgruppe für den angeforderten Befehl in der OLE-Befehl-Zuordnung der Anwendung. Wenn eine Übereinstimmung gefunden wird, wird eine WM_COMMAND-Meldung an die Anwendung, die mit der Befehls-Zuordnung mit der ID der angeforderte Befehl verteilt. (Siehe die Beschreibung der `ON_OLECMD` unten.) Auf diese Weise werden OLE-Befehle an einer Anwendung verteilt in WM_COMMAND-Meldungen von MFC umgewandelt. WM_COMMAND-Meldungen werden dann über der Anwendung meldungszuordnungen mithilfe des MFC-Standards geleitet [Befehlsrouting](../mfc/command-routing.md) Architektur.

Im Gegensatz zu meldungszuordnungen werden die MFC-OLE-befehlszuordnungen von Datensatzfeldern von ClassWizard nicht unterstützt. MFC-Entwickler müssen Unterstützung für die Zuordnung von OLE-Befehl und Zuordnungseinträge für OLE-Befehl manuell hinzufügen. OLE-Befehl, der Zuordnungen MFC Active Document-Server in einer Klasse hinzugefügt werden kann, die in der Kette der WM_COMMAND routing von Nachrichten zum Zeitpunkt das aktive Dokument ist direkt aktiv in einem Container. Diese Klassen umfassen die von abgeleiteten Klassen von der Anwendung [CWinApp](../mfc/reference/cwinapp-class.md), [CView](../mfc/reference/cview-class.md), [CDocument](../mfc/reference/cdocument-class.md), und [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md). In Active Document-Container, OLE-befehlszuordnungen können nur hinzugefügt werden die [COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md)-abgeleitete Klasse. Darüber hinaus in Active Document-Container, die WM_COMMAND-Meldungen nur sind, gesendet werden, die meldungszuordnung in der `COleDocObjectItem`-abgeleitete Klasse.

## <a name="ole-command-map-macros"></a>Ereigniszuordnungs-Makros für OLE-Befehl

Verwenden Sie folgende Makros Befehl Map-Funktionalität Ihrer Klasse hinzu:

```cpp
DECLARE_OLECMD_MAP ()
```

Dieses Makro wird in der Klassendeklaration (in der Regel in der Headerdatei) der Klasse, die die Zuordnung der Befehl enthält.

```cpp
BEGIN_OLECMD_MAP(theClass, baseClass)
```

*theClass*<br/>
Der Name der Klasse, die die Zuordnung der Befehl enthält.

*baseClass*<br/>
Der Name der Basisklasse der Klasse, die die Zuordnung der Befehl enthält.

Dieses Makro markiert den Anfang der Befehl-Zuordnung. Verwenden Sie dieses Makro in der Implementierungsdatei für die Klasse, die die Zuordnung der Befehl enthält.

```
END_OLECMD_MAP()
```

Dieses Makro markiert das Ende der Zuordnung Befehl. Verwenden Sie dieses Makro in der Implementierungsdatei für die Klasse, die die Zuordnung der Befehl enthält. Dieses Makro muss immer das Makro BEGIN_OLECMD_MAP folgen.

```
ON_OLECMD(pguid, olecmdid, id)
```

*pguid*<br/>
Zeiger auf die GUID der Befehlsgruppe für den OLE-Befehl. Dieser Parameter ist **NULL** für die Standardgruppe der OLE-Befehl.

*olecmdid*<br/>
OLE-Befehls-ID des Befehls, der aufgerufen werden.

*ID*<br/>
ID des WM_COMMAND-Meldung gesendet werden, um die Anwendung, die die Befehl-Zuordnung enthält, wenn dieser OLE-Befehl aufgerufen wird.

Verwenden Sie das ON_OLECMD-Makro in der Zuordnung der Befehl zum Hinzufügen von Einträgen für die OLE-Befehle, die Sie behandeln möchten. Wenn die OLE-Befehle empfangen werden, werden sie auf die angegebene WM_COMMAND-Meldung konvertiert und durch Verwenden der MFC-Befehlsrouting Architektur der Anwendung-meldungszuordnung weitergeleitet.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht das Hinzufügen von OLE Befehlsbehandlung Funktion, eine MFC-Active Document-Servers zum Verarbeiten der [OLECMDID_PRINT](/windows/desktop/api/docobj/ne-docobj-olecmdid) OLE-Befehl. In diesem Beispiel wird davon ausgegangen, dass Sie AppWizard verwendet, um eine MFC-Anwendung zu generieren, die einen Active Document-Server entspricht.

1. In Ihrer `CView`-abgeleiteten Klasse die Header-Datei, die DECLARE_OLECMD_MAP-Makro zur Klassendeklaration hinzufügen.

    > [!NOTE]
    > Verwenden der `CView`-Klasse abgeleitet, da sie eine der Klassen im aktiven Dokument-Server ist, die in der Kette der WM_COMMAND routing von Nachrichten ist.

    ```cpp
    class CMyServerView : public CView
    {
    protected: // create from serialization only
        CMyServerView();
        DECLARE_DYNCREATE(CMyServerView)
        DECLARE_OLECMD_MAP()
        // . . .
    };
    ```

2. In der Implementierungsdatei für die `CView`-abgeleitete Klasse sein, fügen Sie die Makros BEGIN_OLECMD_MAP und END_OLECMD_MAP hinzu:

    ```cpp
    BEGIN_OLECMD_MAP(CMyServerView, CView)

    END_OLECMD_MAP()
    ```

3. Um den standardmäßigen OLE Druckbefehl behandeln zu können, fügen eine [ON_OLECMD](reference/message-map-macros-mfc.md#on_olecmd) Makro, um die Befehls-Zuordnung, die die OLE-Befehls-ID für den standard-Drucken-Befehl angeben und **ID_FILE_PRINT** für die WM_COMMAND-ID. **ID_FILE_PRINT** ist der Standard print-Befehls-ID ein, die Anwendungs-Assistenten generierte MFC-Anwendungen:

    ```
    BEGIN_OLECMD_MAP(CMyServerView, CView)
        ON_OLECMD(NULL, OLECMDID_PRINT, ID_FILE_PRINT)
    END_OLECMD_MAP()
    ```

Beachten Sie, dass eine der standard OLE-Befehl definierten Makros afxdocob.h, anstelle der ON_OLECMD-Makro da verwendet werden könnte **OLECMDID_PRINT** ist eine standard OLE-Befehls-ID. Die ON_OLECMD_PRINT-Makro wird die gleiche Aufgabe wie das oben gezeigte ON_OLECMD-Makro zu erreichen.

Wenn eine Container-Anwendung sendet dieser Server eine **OLECMDID_PRINT** Befehl über des Servers des `IOleCommandTarget` -Schnittstelle, die MFC-Bibliothek drucken Befehlshandler wird auf dem Server, und den Server für das Drucken der Anwendungs aufgerufen werden. Active Document-Container-Code zum Aufrufen des print-Befehls in den vorherigen Schritten hinzugefügt würde etwa wie folgt aussehen:

```cpp
void CContainerCntrItem::DoOleCmd()
{
    IOleCommandTarget *pCmd = NULL;
    HRESULT hr = E_FAIL;
    OLECMD ocm={OLECMDID_PRINT, 0};

    hr = m_lpObject->QueryInterface(
        IID_IOleCommandTarget,reinterpret_cast<void**>(&pCmd));

    if (FAILED(hr))
        return;

    hr = pCmd->QueryStatus(NULL, 1, &ocm, NULL);

    if (SUCCEEDED(hr) && (ocm.cmdf& OLECMDF_ENABLED))
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

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
