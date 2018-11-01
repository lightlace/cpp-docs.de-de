---
title: Hinzufügen eines Ereignisses (ATL-Lernprogramm, Teil 5)
ms.custom: get-started-article
ms.date: 09/27/2018
ms.assetid: 2de12022-3148-4ce3-8606-8a9d4274f0e9
ms.openlocfilehash: 4576af12f73e907fa8826ad71185a42ed9b9308e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643039"
---
# <a name="adding-an-event-atl-tutorial-part-5"></a>Hinzufügen eines Ereignisses (ATL-Lernprogramm, Teil 5)

In diesem Schritt fügen Sie eine `ClickIn` und `ClickOut` Ereignis, das ATL-Steuerelement. Sie werden ausgelöst, die `ClickIn` Ereignis klickt der Benutzer innerhalb des Polygons und Fire `ClickOut` klickt der Benutzer außerhalb. Die Aufgaben, die ein Ereignis hinzufügen, lauten wie folgt aus:

- Hinzufügen der `ClickIn` und `ClickOut` Methoden

- Die Typbibliothek generieren

- Implementieren die Verbindungspunkt-Schnittstellen

## <a name="adding-the-clickin-and-clickout-methods"></a>Hinzufügen der ClickIn und ClickOut-Methoden

Bei der Erstellung der ATL-Steuerelement in Schritt 2 ausgewählten der **Verbindungspunkte** Kontrollkästchen. Dies erstellt die `_IPolyCtlEvents` -Schnittstelle in der Datei Polygon.idl. Beachten Sie, dass der Schnittstellenname mit einem Unterstrich beginnt. Dies ist eine Konvention, um anzugeben, dass die Schnittstelle eine interne Schnittstelle ist. Daher können Programme, die Ihnen ermöglichen, die COM-Objekten zu suchen, nicht die Schnittstelle für den Benutzer anzuzeigen. Beachten Sie auch diese Auswahl **Verbindungspunkte** die folgende Zeile hinzugefügt, in der Datei Polygon.idl, um anzugeben, dass `_IPolyCtlEvents` Standard-Quellschnittstelle ist:

`[default, source] dispinterface _IPolyCtlEvents;`

Das Quellattribut gibt an, dass das Steuerelement die Quelle der Benachrichtigungen, damit er diese Schnittstelle für den Container aufrufen wird.

Fügen Sie nun die `ClickIn` und `ClickOut` Methoden, um die `_IPolyCtlEvents` Schnittstelle.

### <a name="to-add-the-clickin-and-clickout-methods"></a>Die Methoden ClickIn und ClickOut hinzufügen

1. In **Projektmappen-Explorer**Polygon.idl öffnen, und fügen Sie den folgenden Code unter `methods:` in die `dispInterface_IPolyCtlEvents` Deklaration der PolygonLib-Bibliothek:

    ```cpp
   [id(1), helpstring("method ClickIn")] void ClickIn([in] LONG x,[in] LONG y);
   [id(2), helpstring("method ClickOut")] void ClickOut([in] LONG x,[in] LONG y);
    ```

Die `ClickIn` und `ClickOut` Methoden verwenden die x- und y-Koordinaten der Punktes als Parameter.

## <a name="generating-the-type-library"></a>Die Typbibliothek generieren

Generieren Sie die Typbibliothek an diesem Punkt aus, da das Projekt kann zum Abrufen der benötigten Informationen, um einen Verbindungspunkt-Schnittstelle und einen Verbindungspunkt Container-Schnittstelle für das Steuerelement zu erstellen.

### <a name="to-generate-the-type-library"></a>Um die Typbibliothek zu generieren.

1. Erstellen Sie Ihr Projekt neu.

     - oder - 

1. Mit der rechten Maustaste in der Datei Polygon.idl in **Projektmappen-Explorer** , und klicken Sie auf **Kompilieren** im Kontextmenü auf.

Dadurch wird die Polygon.tlb-Datei erstellt, die die Typbibliothek ist. Die Datei Polygon.tlb nicht sichtbar ist **Projektmappen-Explorer**, da es eine binäre Datei ist kann nicht angezeigt oder direkt bearbeitet werden.

## <a name="implementing-the-connection-point-interfaces"></a>Implementieren die Verbindungspunkt-Schnittstellen

Implementieren Sie einen Verbindungspunkt-Schnittstelle und einen Verbindungspunkt Container-Schnittstelle für das Steuerelement. In COM werden Ereignisse über den Mechanismus der Verbindungspunkte implementiert. Zum Empfangen von Ereignissen aus einem COM-Objekt stellt ein Container an den Verbindungspunkt, den das COM-Objekt implementiert eine Advise-Verbindung her. Da ein COM-Objekt mehrere Verbindungspunkte verfügen kann, implementiert das COM-Objekt auch eine Verbindungspunkt Container-Schnittstelle. Über diese Schnittstelle kann der Container bestimmen, welche Verbindungspunkte unterstützt werden.

Die Schnittstelle, die implementiert einen Verbindungspunkt heißt `IConnectionPoint`, und die Schnittstelle, eine Verbindungspunktcontainer implementiert, heißt `IConnectionPointContainer`.

Um implementieren `IConnectionPoint`, verwenden Sie den Assistent zum Implementieren von Verbindungspunkten. Dieser Assistent generiert die `IConnectionPoint` -Schnittstelle durch die Typbibliothek liest und implementiert eine Funktion für jedes Ereignis, das ausgelöst werden kann.

### <a name="to-implement-the-connection-points"></a>Um die Verbindungspunkte zu implementieren.

1. In **Projektmappen-Explorer**_IPolyCtlEvents_CP.h öffnen, und fügen Sie den folgenden Code unter der `public:` -Anweisung in der `CProxy_IPolyCtlEvents` Klasse:

    ```cpp
    VOID Fire_ClickIn(LONG x, LONG y)
    {
        T* pT = static_cast<T*>(this);
        int nConnectionIndex;
        CComVariant* pvars = new CComVariant[2];
        int nConnections = m_vec.GetSize();

        for (nConnectionIndex = 0; nConnectionIndex < nConnections; nConnectionIndex++)
        {
            pT->Lock();
            CComPtr<IUnknown> sp = m_vec.GetAt(nConnectionIndex);
            pT->Unlock();
            IDispatch* pDispatch = reinterpret_cast<IDispatch*>(sp.p);
            if (pDispatch != NULL)
            {
                pvars[1].vt = VT_I4;
                pvars[1].lVal = x;
                pvars[0].vt = VT_I4;
                pvars[0].lVal = y;
                DISPPARAMS disp = { pvars, NULL, 2, 0 };
                pDispatch->Invoke(0x1, IID_NULL, LOCALE_USER_DEFAULT, DISPATCH_METHOD, &disp, NULL, NULL, NULL);
            }
        }
        delete[] pvars;

    }
    VOID Fire_ClickOut(LONG x, LONG y)
    {
        T* pT = static_cast<T*>(this);
        int nConnectionIndex;
        CComVariant* pvars = new CComVariant[2];
        int nConnections = m_vec.GetSize();

        for (nConnectionIndex = 0; nConnectionIndex < nConnections; nConnectionIndex++)
        {
            pT->Lock();
            CComPtr<IUnknown> sp = m_vec.GetAt(nConnectionIndex);
            pT->Unlock();
            IDispatch* pDispatch = reinterpret_cast<IDispatch*>(sp.p);
            if (pDispatch != NULL)
            {
                pvars[1].vt = VT_I4;
                pvars[1].lVal = x;
                pvars[0].vt = VT_I4;
                pvars[0].lVal = y;
                DISPPARAMS disp = { pvars, NULL, 2, 0 };
                pDispatch->Invoke(0x2, IID_NULL, LOCALE_USER_DEFAULT, DISPATCH_METHOD, &disp, NULL, NULL, NULL);
            }
        }
        delete[] pvars;

    }
    ```

Sie sehen, dass diese Datei eine Klasse namens hat `CProxy_IPolyCtlEvents` abgeleitet, die `IConnectionPointImpl`. _IPolyCtlEvents_CP.h definiert nun die beiden Methoden `Fire_ClickIn` und `Fire_ClickOut`, dies die zwei Koordinatenparameter dauern. Sie aufrufen diese Methoden, wenn Sie zum Auslösen eines Ereignisses über das Steuerelement möchten.

Erstellen Sie das Steuerelement mit **Verbindungspunkte** Option ausgewählt ist, ist die _IPolyCtlEvents_CP.h-Datei für Sie generiert wurde. IT auch hinzugefügt `CProxy_PolyEvents` und `IConnectionPointContainerImpl` Ihres Steuerelements mehrere Vererbung Liste und `IConnectionPointContainer` für Sie von der COM-Zuordnung entsprechende Einträge hinzugefügt.

Sie sind fertig, implementieren den Code, um Ereignisse zu unterstützen. Nun fügen Sie Code zum Auslösen der Ereignisse zum entsprechenden Zeitpunkt. Beachten Sie, dass Sie ausgelöst werden soll eine `ClickIn` oder `ClickOut` Ereignis aus, wenn der Benutzer die linke Maustaste im Steuerelement klickt. Um herauszufinden, wenn der Benutzer die Schaltfläche klickt, fügen Sie einen Handler für die `WM_LBUTTONDOWN` Nachricht.

### <a name="to-add-a-handler-for-the-wmlbuttondown-message"></a>Um einen Handler für die Nachricht WM_LBUTTONDOWN hinzuzufügen

1. In **Klassenansicht**, mit der rechten Maustaste die `CPolyCtl` Klasse, und klicken Sie auf **Eigenschaften** im Kontextmenü auf.

1. In der **Eigenschaften** Fenster, klicken Sie auf die **Nachrichten** Symbol, und klicken Sie dann auf `WM_LBUTTONDOWN` aus der Liste auf der linken Seite.

1. Aus der Dropdown-Liste, die angezeigt wird, klicken Sie auf  **\<hinzufügen > OnLButtonDown**. Die `OnLButtonDown` PolyCtl.h Handlerdeklaration hinzugefügt, und die Implementierung des Handlers wird PolyCtl.cpp hinzugefügt werden.

Als Nächstes ändern Sie den Ereignishandler an.

### <a name="to-modify-the-onlbuttondown-method"></a>So ändern Sie die OnLButtonDown-Methode

1. Ändern Sie den Code, der besteht aus den `OnLButtonDown` -Methode in der PolyCtl.cpp (Löschen keinen Code, der vom Assistenten platziert), damit sie wie folgt aussieht:

    [!code-cpp[NVC_ATL_Windowing#57](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_2.cpp)]

Dieser Code macht mithilfe der Punkte berechnet, in der `OnDraw` Funktion, um einen Bereich zu erstellen, die erkennt, Mausklicks des Benutzers durch den Aufruf von `PtInRegion`.

Die *uMsg* Parameter ist die ID der Nachricht Windows behandelt werden. Dadurch können Sie eine Funktion verfügen, die einen Bereich von Nachrichten verarbeitet. Die *wParam* und *lParam* Parameter sind die Standardwerte für die Nachricht verarbeitet. Der Parameter *bHandled* können Sie angeben, ob die Funktion die Meldung behandelt wurde oder nicht. Standardmäßig ist der Wert auf "true" festgelegt, um anzugeben, dass die Funktion die Meldung verarbeitet wurde, aber Sie können sie auf "false" festlegen. Dies bewirkt, ATL, um den Vorgang fortzusetzen, für eine andere Nachricht Handler-Funktion zum Senden der Nachricht zu suchen.

## <a name="building-and-testing-the-control"></a>Erstellen und Testen des Steuerelements

Probieren Sie jetzt Ihre Events ein. Erstellen Sie das Steuerelement, und starten Sie den Testcontainer für ActiveX-Steuerelemente. Rufen Sie dieses Mal das Ereignisprotokoll-Fenster. Zum Weiterleiten von Ereignissen in das Ausgabefenster, klicken Sie auf **Protokollierung** aus der **Optionen** Menü **Protokoll, um das Fenster "Ausgabe"**. Fügen Sie das Steuerelement, und klicken Sie im Fenster auf. Beachten Sie, dass `ClickIn` wird ausgelöst, wenn Sie innerhalb der gefülltes Polygon klicken und `ClickOut` wird ausgelöst, wenn Sie außerhalb davon klicken.

Als Nächstes fügen Sie auf einer Eigenschaftenseite.

[Zurück zu Schritt 4](../atl/changing-the-drawing-code-atl-tutorial-part-4.md) &#124; [mit Schritt 6 fort](../atl/adding-a-property-page-atl-tutorial-part-6.md)

## <a name="see-also"></a>Siehe auch

[Tutorial](../atl/active-template-library-atl-tutorial.md)
