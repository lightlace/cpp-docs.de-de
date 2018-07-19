---
title: 'TN071: MFC-IOleCommandTarget-Implementierung | Microsoft Docs'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- IOleCommandTarget
dev_langs:
- C++
helpviewer_keywords:
- TN071 [MFC]
- IOleCommandTarget interface [MFC]
ms.assetid: 3eef571e-6357-444d-adbb-6f734a0c3161
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ebd796690407fe0e65bc790c52477c7e4d149250
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122620"
---
# <a name="tn071-mfc-iolecommandtarget-implementation"></a>TN071: MFC-IOleCommandTarget-Implementierung

> [!NOTE]
> Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

Die `IOleCommandTarget` Schnittstelle ermöglicht, Objekte und deren Container, Befehle aus, um miteinander zu versenden. Z. B. ein Objekt Symbolleisten möglicherweise enthalten Sie Schaltflächen für Befehle wie z. B. `Print`, `Print Preview`, `Save`, `New`, und `Zoom`. Wenn ein solches Objekt in einem Container, die unterstützt eingebettet wurden `IOleCommandTarget`, das Objekt konnte aktivieren Sie die Schaltflächen und Weiterleiten der Befehle auf den Container für die Verarbeitung, wenn der Benutzer, die sie geklickt haben. Wenn ein Container das eingebettete Objekt selbst drucken möchten, konnte erleichtern diese Anforderung durch Senden eines Befehls über die `IOleCommandTarget` Schnittstelle des eingebetteten Objekts.

`IOleCommandTarget` eine Automation-ähnliche Schnittstelle ist, da er von einem Client zum Aufrufen von Methoden auf einem Server verwendet wird. Allerdings `IOleCommandTarget` spart den Mehraufwand der Aufrufe über Automatisierungsschnittstellen, da Programmierer nicht verwenden, die in der Regel aufwändige `Invoke` Methode `IDispatch`.

In MFC können die `IOleCommandTarget` Schnittstelle wird von Server für aktive Dokumente verwendet, um Active Document-Container auf dispatch-Befehle an den Server zu ermöglichen. Das aktive Dokument Serverklasse `CDocObjectServerItem`, verwendet MFC-schnittstellenzuordnungen (finden Sie unter [tn038 Implementieren von: MFC/OLE-IUnknown-Implementierung](../mfc/tn038-mfc-ole-iunknown-implementation.md)) zum Implementieren der `IOleCommandTarget` Schnittstelle.

`IOleCommandTarget` wird auch im implementiert die `COleFrameHook` Klasse. `COleFrameHook` ist eine nicht dokumentierte MFC-Klasse, die die Frame-Fensterfunktionalität direkte Bearbeitung Container implementiert. `COleFrameHook` verwendet auch die MFC-schnittstellenzuordnungen zum Implementieren der `IOleCommandTarget` Schnittstelle. `COleFrameHook`der Implementierung von `IOleCommandTarget` leitet der OLE-Befehle zum `COleDocObjectItem`-abgeleitete Active Document-Container. Dadurch werden alle MFC Active Document-Container zum Empfangen von Nachrichten von enthaltene Active Document-Servern.

## <a name="mfc-ole-command-maps"></a>MFC-OLE-Befehl Zuordnungen

MFC-Entwickler nutzen `IOleCommandTarget` mit MFC OLE Befehl zugeordnet. OLE-Befehl-Karten sind wie meldungszuordnungen, da sie verwendet werden können, um OLE-Befehle Memberfunktionen der Klasse zuordnen, die Zuordnung der Befehl enthält. Damit dies funktioniert, platzieren Sie Makros in der Zuordnung Befehl, geben Sie die OLE-Befehl-Gruppe des Befehls, die Sie behandeln möchten, die OLE-Befehl und die Befehls-ID des dem [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Meldung, die gesendet wird, wenn der OLE-Befehl empfangen wird. MFC enthält außerdem eine Reihe von vordefinierten Makros für OLE-Standardbefehle. Eine Liste der standard OLE-Befehle, die zur ursprünglich entwickelt wurden mit Microsoft Office-Anwendungen verwenden, finden Sie unter der OLECMDID-Enumeration, die in docobj.h definiert ist.

Wenn ein OLE-Befehl von einer MFC_Anwendung, die eine Zuordnung der OLE-Befehl enthält empfangen wird, versucht MFC die Befehls-ID und die Befehlsgruppe für den angeforderten Befehl in der OLE-Befehl-Zuordnung der Anwendung zu suchen. Wenn eine Übereinstimmung gefunden wird, wird eine WM_COMMAND-Nachricht an die Anwendung mit dem Befehl-Zuordnung mit der ID der angeforderte Befehl verteilt. (Siehe die Beschreibung der `ON_OLECMD` unten.) Auf diese Weise werden die OLE-Befehle, die an eine Anwendung zugestellt wurden in WM_COMMAND-Meldungen von MFC aktiviert. WM_COMMAND-Meldungen klicken Sie dann über die Anwendung den meldungszuordnungen mit den standardmäßigen MFC weitergeleitet [Befehlsrouting](../mfc/command-routing.md) Architektur.

Im Gegensatz zu den meldungszuordnungen werden die Zuordnungen für das MFC-OLE-Befehl von ClassWizard nicht unterstützt. MFC-Entwickler müssen OLE-Befehl der Unterstützung von Karten und OLE-Befehl-Zuordnungseinträge manuell hinzufügen. OLE-Befehl Maps MFC Active Document-Server in einer Klasse hinzugefügt werden können, die in der Kette der WM_COMMAND routing von Nachrichten zum Zeitpunkt des aktiven Dokuments ist in-Place aktiv in einem Container. Diese Klassen umfassen von abgeleiteten Klassen für die Anwendung [CWinApp](../mfc/reference/cwinapp-class.md), [CView](../mfc/reference/cview-class.md), [CDocument](../mfc/reference/cdocument-class.md), und [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md). In Active Document-Container OLE-Befehl Zuordnungen können nur hinzugefügt werden die [COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md)-Klasse. Darüber hinaus in Active Document-Container WM_COMMAND-Meldungen werden nur weitergeleitet werden, die meldungszuordnung in der `COleDocObjectItem`-Klasse.

## <a name="ole-command-map-macros"></a>Ereigniszuordnungs-Makros für OLE-Befehl

Verwenden Sie folgende Makros, Ihre Klasse kartenfunktion Befehl hinzu:

```cpp
DECLARE_OLECMD_MAP ()
```

Dieses Makro wird in der Klassendeklaration (in der Regel in der Headerdatei) der Klasse, die die Zuordnung der Befehl enthält.

```cpp
BEGIN_OLECMD_MAP(theClass, baseClass)
```

*theClass*  
 Der Name der Klasse, die die Zuordnung der Befehl enthält.

*baseClass*  
 Der Name der Basisklasse der Klasse, die die Zuordnung der Befehl enthält.

Dieses Makro markiert den Beginn der Zuordnung Befehl. Verwenden Sie dieses Makro in der Implementierungsdatei für die Klasse, die die Zuordnung der Befehl enthält.

```
END_OLECMD_MAP()
```

Dieses Makro markiert das Ende der Zuordnung Befehl. Verwenden Sie dieses Makro in der Implementierungsdatei für die Klasse, die die Zuordnung der Befehl enthält. Dieses Makro muss immer das Makro BEGIN_OLECMD_MAP folgen.

```
ON_OLECMD(pguid, olecmdid, id)
```

*pguid*  
 Zeiger auf die GUID der Befehlsgruppe der OLE-Befehl. Dieser Parameter ist **NULL** für die Gruppe der standard OLE-Befehl.

*olecmdid*  
 OLE-Befehls-ID des Befehls, aufgerufen werden soll.

*ID*  
 Die ID der WM_COMMAND-Nachricht gesendet werden, um die Anwendung mit der Befehls-Zuordnung aus, wenn der OLE-Befehl aufgerufen wird.

Verwenden Sie das ON_OLECMD-Makro in der Zuordnung Befehl Einträge für die OLE-Befehle hinzufügen, die Sie behandeln möchten. Wenn die OLE-Befehle empfangen werden, werden sie in der angegebenen WM_COMMAND-Nachricht konvertiert und über die Anwendung meldungszuordnung, die mit der MFC-Befehlsrouting Architektur weitergeleitet werden.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht das Hinzufügen von OLE befehlsverarbeitung Funktion auf ein MFC Active Document-Server behandelt die [OLECMDID_PRINT](http://msdn.microsoft.com/library/windows/desktop/ms691264) OLE-Befehl. In diesem Beispiel wird davon ausgegangen, dass Sie AppWizard verwendet, um eine MFC-Anwendung zu generieren, die einen Active Document-Server entspricht.

1. In Ihrer `CView`-abgeleitete Klasse des Header-Datei, fügen Sie der Klassendeklaration das DECLARE_OLECMD_MAP-Makro.

    > [!NOTE]
    > Verwenden der `CView`-Klasse abgeleitet, da es eine der Klassen in der Active Document-Server handelt, die in der WM_COMMAND Nachrichtenrouting Kette ist.

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

2. In der Implementierungsdatei für die `CView`-abgeleitete Klasse, die Makros BEGIN_OLECMD_MAP und END_OLECMD_MAP hinzufügen:

    ```cpp
    BEGIN_OLECMD_MAP(CMyServerView, CView)

    END_OLECMD_MAP()
    ```

3. Um der standard OLE-Druckbefehl behandeln zu können, fügen Sie ein [ON_OLECMD](reference/message-map-macros-mfc.md#on_olecmd) Makro zur Angabe der OLE-Befehls-ID für den Druck Standardbefehl Befehl Zuordnung und **ID_FILE_PRINT** für die WM_COMMAND-ID. **ID_FILE_PRINT** der print-Befehls-ID, die von AppWizard generierte MFC-Anwendungen verwendete Standard ist:

    ```
    BEGIN_OLECMD_MAP(CMyServerView, CView)
        ON_OLECMD(NULL, OLECMDID_PRINT, ID_FILE_PRINT)
    END_OLECMD_MAP()
    ```

Beachten Sie, dass der OLE-Befehl Standardmakros definiert, die in afxdocob.h, anstelle der ON_OLECMD-Makro da verwendet werden konnte **OLECMDID_PRINT** ist eine standard OLE-Befehls-ID. ON_OLECMD_PRINT-Makro wird die gleiche Aufgabe wie die oben gezeigte ON_OLECMD-Makro zu erreichen.

Wenn eine Steuerelementcontainer-Anwendung sendet dieser Server eine **OLECMDID_PRINT** Befehl über des Servers `IOleCommandTarget` -Schnittstelle, die MFC-Bibliothek drucken Befehlshandler wird auf dem Server, wenn der Server So drucken Sie die Anwendung aufgerufen werden. Active Document-Container-Code zum Aufrufen der Druckbefehl in den vorhergehenden Schritten hinzugefügt würde etwa wie folgt aussehen:

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

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)  
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)  
