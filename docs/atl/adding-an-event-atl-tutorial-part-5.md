---
title: Hinzufügen eines Ereignisses (ATL-Lernprogramm, Teil 5)
ms.custom: get-started-article
ms.date: 09/27/2018
ms.assetid: 2de12022-3148-4ce3-8606-8a9d4274f0e9
ms.openlocfilehash: c9a7c6f38a2f47ec808081e440a200737ad1928a
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127573"
---
# <a name="adding-an-event-atl-tutorial-part-5"></a>Hinzufügen eines Ereignisses (ATL-Lernprogramm, Teil 5)

In diesem Schritt fügen Sie dem ATL-Steuerelement eine `ClickIn` und ein `ClickOut`-Ereignis hinzu. Sie lösen das `ClickIn` Ereignis aus, wenn der Benutzer auf das Polygon klickt und `ClickOut` ausgelöst wird, wenn der Benutzer auf außerhalb klickt. Die Aufgaben zum Hinzufügen eines Ereignisses lauten wie folgt:

- Hinzufügen der Methoden `ClickIn` und `ClickOut`

- Erstellen der Typbibliothek

- Implementieren der Verbindungspunkt Schnittstellen

## <a name="adding-the-clickin-and-clickout-methods"></a>Hinzufügen der ClickIn-und ClickOut-Methoden

Wenn Sie in Schritt 2 das ATL-Steuerelement erstellt haben, haben Sie das Kontrollkästchen **Verbindungspunkte** ausgewählt. Dadurch wurde die `_IPolyCtlEvents`-Schnittstelle in der Polygon. IDL-Datei erstellt. Beachten Sie, dass der Schnittstellen Name mit einem Unterstrich beginnt. Dies ist eine Konvention, die angibt, dass die Schnittstelle eine interne Schnittstelle ist. Programme, die es Ihnen ermöglichen, com-Objekte zu durchsuchen, können also auswählen, dass die Benutzeroberfläche für den Benutzer nicht angezeigt wird. Beachten Sie außerdem, dass durch Auswählen von **Verbindungs Punkten** die folgende Zeile in der Polygon. IDL-Datei hinzugefügt wurde, um anzugeben, dass `_IPolyCtlEvents` die standardmäßige Quell Schnittstelle ist

`[default, source] dispinterface _IPolyCtlEvents;`

Das Quell Attribut gibt an, dass das Steuerelement die Quelle der Benachrichtigungen ist, sodass diese Schnittstelle für den Container aufgerufen wird.

Fügen Sie nun der `_IPolyCtlEvents`-Schnittstelle die Methoden `ClickIn` und `ClickOut` hinzu.

### <a name="to-add-the-clickin-and-clickout-methods"></a>So fügen Sie die ClickIn-und die ClickOut-Methode hinzu

1. Öffnen Sie in **Projektmappen-Explorer**Polygon. idl, und fügen Sie den folgenden Code unter `methods:` in der `dispInterface_IPolyCtlEvents`-Deklaration der PolygonLib-Bibliothek ein:

    ```cpp
   [id(1), helpstring("method ClickIn")] void ClickIn([in] LONG x,[in] LONG y);
   [id(2), helpstring("method ClickOut")] void ClickOut([in] LONG x,[in] LONG y);
    ```

Die Methoden `ClickIn` und `ClickOut` übernehmen die x-und y-Koordinaten des angeklickten Punkts als Parameter.

## <a name="generating-the-type-library"></a>Erstellen der Typbibliothek

Generieren Sie an dieser Stelle die Typbibliothek, da das Projekt diese zum Abrufen der Informationen verwendet, die zum Erstellen einer Verbindungspunkt Schnittstelle und einer Verbindungspunkt-Container Schnittstelle für das Steuerelement benötigt werden.

### <a name="to-generate-the-type-library"></a>So generieren Sie die Typbibliothek

1. Erstellen Sie das Projekt neu.

     Oder

1. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei Polygon. idl, und klicken Sie im Kontextmenü auf **Kompilieren** .

Dadurch wird die Datei "Polygon. tlb" erstellt, bei der es sich um die Typbibliothek handelt. Die Datei "Polygon. tlb" ist aus **Projektmappen-Explorer**nicht sichtbar, da es sich um eine Binärdatei handelt, die nicht direkt angezeigt oder bearbeitet werden kann.

## <a name="implementing-the-connection-point-interfaces"></a>Implementieren der Verbindungspunkt Schnittstellen

Implementieren Sie eine Verbindungspunkt Schnittstelle und eine Verbindungspunkt-Container Schnittstelle für das Steuerelement. In com werden Ereignisse über den Mechanismus von Verbindungs Punkten implementiert. Zum Empfangen von Ereignissen von einem COM-Objekt stellt ein Container eine Beratungs Verbindung mit dem Verbindungspunkt her, den das COM-Objekt implementiert. Da ein COM-Objekt mehrere Verbindungspunkte aufweisen kann, implementiert das COM-Objekt auch eine Verbindungspunkt-Container Schnittstelle. Über diese Schnittstelle kann der Container ermitteln, welche Verbindungspunkte unterstützt werden.

Die Schnittstelle, die einen Verbindungspunkt implementiert, wird als `IConnectionPoint`bezeichnet, und die Schnittstelle, die einen Verbindungspunkt Container implementiert, wird als `IConnectionPointContainer`bezeichnet.

Zur Unterstützung der Implementierung von `IConnectionPoint`verwenden Sie den Assistenten zum Implementieren von Verbindungs Punkten. Dieser Assistent generiert die `IConnectionPoint`-Schnittstelle, indem er die Typbibliothek liest und eine Funktion für jedes Ereignis implementiert, das ausgelöst werden kann.

### <a name="to-implement-the-connection-points"></a>So implementieren Sie die Verbindungspunkte

1. Öffnen Sie in **Projektmappen-Explorer**_IPolyCtlEvents_CP. h, und fügen Sie den folgenden Code unter der `public:`-Anweisung in der `CProxy_IPolyCtlEvents`-Klasse ein:

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

Sie werden feststellen, dass diese Datei über eine Klasse namens "`CProxy_IPolyCtlEvents`" verfügt, die von `IConnectionPointImpl`abgeleitet ist. _IPolyCtlEvents_CP. h definiert nun die beiden Methoden `Fire_ClickIn` und `Fire_ClickOut`, die die beiden Koordinaten Parameter annehmen. Diese Methoden werden aufgerufen, wenn Sie ein Ereignis aus dem Steuerelement auslösen möchten.

Wenn Sie die Option Steuerelement mit **Verbindungs Punkten** erstellen ausgewählt haben, wurde die Datei _IPolyCtlEvents_CP. h für Sie generiert. Außerdem wurden der mehrfach Vererbungs Liste Ihres Steuer Elements `CProxy_PolyEvents` und `IConnectionPointContainerImpl` hinzugefügt und `IConnectionPointContainer` für Sie verfügbar gemacht, indem der com-Zuordnung entsprechende Einträge hinzugefügt werden.

Die Implementierung des Codes zum unterstützen von Ereignissen ist abgeschlossen. Fügen Sie nun Code hinzu, um die Ereignisse zu einem passenden Zeitpunkt auszulösen. Beachten Sie, dass Sie ein `ClickIn` oder `ClickOut` Ereignis auslösen, wenn der Benutzer auf die linke Maustaste im Steuerelement klickt. Um herauszufinden, wann der Benutzer auf die Schaltfläche klickt, fügen Sie einen Handler für die `WM_LBUTTONDOWN` Nachricht hinzu.

### <a name="to-add-a-handler-for-the-wm_lbuttondown-message"></a>So fügen Sie einen Handler für die WM_LBUTTONDOWN Nachricht hinzu

1. Klicken Sie in **Klassenansicht**mit der rechten Maustaste auf die Klasse `CPolyCtl`, und klicken Sie im Kontextmenü auf **Eigenschaften** .

1. Klicken Sie im Fenster **Eigenschaften** auf das Symbol **Meldungen** , und klicken Sie dann in der Liste auf der linken Seite auf `WM_LBUTTONDOWN`.

1. Klicken Sie in der Dropdown Liste, die angezeigt wird, auf **\<> OnLButtonDown hinzufügen**. Die `OnLButtonDown` Handlerdeklaration wird PolyCtl. h hinzugefügt, und die Handlerimplementierung wird PolyCtl. cpp hinzugefügt.

Ändern Sie als nächstes den Handler.

### <a name="to-modify-the-onlbuttondown-method"></a>So ändern Sie die OnLButtonDown-Methode

1. Ändern Sie den Code, der die `OnLButtonDown` Methode in PolyCtl. cpp enthält (löscht jeglichen vom Assistenten platzierten Code), sodass er wie folgt aussieht:

    [!code-cpp[NVC_ATL_Windowing#57](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_2.cpp)]

In diesem Code werden die in der `OnDraw`-Funktion berechneten Punkte verwendet, um einen Bereich zu erstellen, der die Mausklicks des Benutzers mit dem Aufrufen von `PtInRegion`erkennt.

Der *uMsg* -Parameter ist die ID der zu behandelnden Windows-Meldung. Auf diese Weise können Sie über eine Funktion verfügen, die eine Reihe von Nachrichten verarbeitet. Der *wParam* -Parameter und der *LPARAM* -Parameter sind die Standardwerte für die behandelte Nachricht. Mit dem *bbehandelte* Parameter können Sie angeben, ob die Funktion die Nachricht verarbeitet hat. Standardmäßig ist der Wert auf true festgelegt, um anzugeben, dass die Funktion die Nachricht verarbeitet hat, Sie können Sie jedoch auf false festlegen. Dies bewirkt, dass ATL weiterhin nach einer anderen nachrichtenhandlerfunktion sucht, an die die Nachricht gesendet wird.

## <a name="building-and-testing-the-control"></a>Erstellen und Testen des Steuerelements

Testen Sie Ihre Ereignisse nun. Erstellen Sie das Steuerelement, und starten Sie den Test Container des ActiveX-Steuer Elements erneut Sehen Sie sich dieses Mal das Fenster Ereignisprotokoll an. Um Ereignisse an das Ausgabefenster weiterzuleiten, klicken Sie im Menü **Optionen** auf **Protokollierung** , und wählen Sie dann im **Fenster Protokoll anmelden**aus. Fügen Sie das Steuerelement ein, und klicken Sie im Fenster auf. Beachten Sie, dass `ClickIn` ausgelöst wird, wenn Sie innerhalb des gefüllten Polygons klicken und `ClickOut` ausgelöst wird, wenn Sie außerhalb des Polygons klicken.

Als Nächstes fügen Sie eine Eigenschaften Seite hinzu.

[Zurück zu Schritt 4](../atl/changing-the-drawing-code-atl-tutorial-part-4.md) &#124; für [Schritt 6](../atl/adding-a-property-page-atl-tutorial-part-6.md)

## <a name="see-also"></a>Weitere Informationen

[Tutorial](../atl/active-template-library-atl-tutorial.md)
