---
title: 'TN065: Unterstützung für duale Schnittstellen für OLE-Automatisierungsserver | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.ole
dev_langs:
- C++
helpviewer_keywords:
- dual interfaces [MFC], OLE Automation
- TN065 [MFC]
- ACDUAL sample [MFC]
- Automation servers [MFC], dual-interface support
ms.assetid: b5c8ed09-2f7f-483c-80fc-2a47ad896063
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 837149397ec45ebd8b41808b170b9f5e25146d6a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387691"
---
# <a name="tn065-dual-interface-support-for-ole-automation-servers"></a>TN065: Unterstützung für duale Schnittstellen für OLE-Automatisierungsserver

> [!NOTE]
> Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

Dieser Hinweis enthält, wie eine Anwendung mit OLE-Automatisierungsserver MFC-basierten Unterstützung für duale Schnittstellen hinzugefügt wird. Die [ACDUAL](../visual-cpp-samples.md) Beispiel veranschaulicht die Unterstützung für duale Schnittstellen und der Beispielcode in diesem Hinweis ACDUAL entnommen wird. Die Makros, die in diesem Beachten Sie, wie z. B. DECLARE_DUAL_ERRORINFO DUAL_ERRORINFO_PART und IMPLEMENT_DUAL_ERRORINFO, sind Teil der ACDUAL-Beispiel und in MFCDUAL befinden. H.

## <a name="dual-interfaces"></a>Duale Schnittstellen

OLE-Automatisierung können Sie implementieren eine `IDispatch` -Schnittstelle, eine VTBL-Schnittstelle oder eine duale Schnittstelle (die beide umfasst), empfiehlt Microsoft dringend, dass Sie duale Schnittstellen implementieren, für alle OLE-Automatisierungsobjekte verfügbar gemacht. Duale Schnittstellen haben bedeutende Vorteile gegenüber `IDispatch`- oder nur VTBL-Schnittstellen:

- Bindung kann stattfinden zum Zeitpunkt der Kompilierung über die VTBL-Schnittstelle oder zur Laufzeit durch `IDispatch`.

- OLE-Automatisierungscontroller, die von der VTBL-Schnittstelle verwenden können, können von einer verbesserten Leistung profitieren.

- Vorhandene OLE-Automatisierungscontroller, mit denen die `IDispatch` Benutzeroberfläche wird weiterhin funktionieren.

- Die VTBL-Schnittstelle ist einfacher, die von C++ aus aufzurufen.

- Duale Schnittstellen sind erforderlich, für die Kompatibilität mit Features für die Unterstützung von Visual Basic-Objekt.

## <a name="adding-dual-interface-support-to-a-ccmdtarget-based-class"></a>Hinzufügen von Unterstützung für duale Schnittstellen zu einer CCmdTarget-basierte-Klasse

Eine duale Schnittstelle ist eigentlich nur eine benutzerdefinierte Schnittstelle, die von abgeleiteten `IDispatch`. Die einfachste Methode zum Implementieren von Unterstützung für duale Schnittstellen in einem `CCmdTarget`-Basis-Klasse ist das erste implementieren die normalen Verteilung Schnittstelle in Ihrer Klasse, die mit MFC und Klassen-Assistenten auf, und klicken Sie dann die benutzerdefinierte Schnittstelle später hinzufügen. Zum größten Teil Ihrer Implementierung eines benutzerdefinierten einfach delegiert die zurück an die MFC-Bibliothek `IDispatch` Implementierung.

Ändern Sie zunächst die ODL-Datei für den Server aus, um duale Schnittstellen für Ihre Objekte zu definieren. Sie müssen eine Interface-Anweisung, um eine duale Schnittstelle zu definieren, verwenden, anstatt die `DISPINTERFACE` -Anweisung, die die Visual C++-Assistenten generieren. Anstatt zu entfernen, die vorhandene `DISPINTERFACE` -Anweisung, fügen Sie eine neue Schnittstelle-Anweisung hinzu. Durch Beibehalten der `DISPINTERFACE` Formular können Sie weiterhin Klassen-Assistenten zu verwenden, um die Eigenschaften und Methoden für Ihr Objekt hinzufügen, aber Sie müssen die entsprechenden Eigenschaften und Methoden der Schnittstelle-Anweisung hinzufügen.

Eine Interface-Anweisung für eine duale Schnittstelle müssen die *OLEAUTOMATION* und *DUAL* Attribute und die Schnittstelle muss von abgeleitet werden `IDispatch`. Können Sie die [GUIDGEN](../visual-cpp-samples.md) ein Beispiel zum Erstellen einer **IID** für die duale Schnittstelle:

```IDL
[ uuid(0BDD0E81-0DD7-11cf-BBA8-444553540000), // IID_IDualAClick
    oleautomation,
    dual
]
interface IDualAClick : IDispatch
    {
    };
```

Nachdem Sie die Interface-Anweisung eingerichtet haben, starten Sie die Einträge für die Methoden und Eigenschaften hinzufügen. Für duale Schnittstellen müssen Sie die Parameterlisten neu anordnen, dass Ihre Methoden und die Eigenschaft Accessor-Funktionen in der dualen Schnittstelle zurückgeben einer **HRESULT** und übergeben Sie die Rückgabewerte als Parameter mit den Attributen `[retval,out]`. Beachten Sie, dass die Eigenschaften, Sie müssen sowohl einen Lesevorgang hinzufügen (`propget`) und Schreiben (`propput`)-Funktion mit der gleichen Id zugreifen. Zum Beispiel:

```IDL
[propput, id(1)] HRESULT text([in] BSTR newText);
[propget, id(1)] HRESULT text([out, retval] BSTR* retval);
```

Nachdem Ihre Methoden und Eigenschaften definiert wurden, müssen Sie einen Verweis auf die Interface-Anweisung in der Co-Klasse-Anweisung hinzufügen. Zum Beispiel:

```IDL
[ uuid(4B115281-32F0-11cf-AC85-444553540000) ]
coclass Document
{
    dispinterface IAClick;
    [default] interface IDualAClick;
};
```

Sobald Ihre ODL-Datei aktualisiert wurde, verwenden Sie schnittstellenzuordnungsmechanismus von MFC definieren eine Implementierungsklasse, für die duale Schnittstelle in der Objektklasse und die entsprechenden Einträge in MFC `QueryInterface` Mechanismus. Sie benötigen einen Eintrag in der `INTERFACE_PART` Block für jeden Eintrag in der Anweisung Schnittstelle die ODL sowie die Einträge für eine Dispatch-Schnittstelle. Jeder ODL-Eintrag mit der *Propput* Attribut benötigt eine Funktion namens `put_propertyname`. Jeder Eintrag mit der *Propget* Attribut benötigt eine Funktion namens `get_propertyname`.

Eine Implementierungsklasse für die duale Schnittstelle definieren möchten, fügen einen `DUAL_INTERFACE_PART` Block auf Ihre Objektklassendefinition. Zum Beispiel:

```cpp
BEGIN_DUAL_INTERFACE_PART(DualAClick, IDualAClick)
    STDMETHOD(put_text)(THIS_ BSTR newText);
    STDMETHOD(get_text)(THIS_ BSTR FAR* retval);
    STDMETHOD(put_x)(THIS_ short newX);
    STDMETHOD(get_x)(THIS_ short FAR* retval);
    STDMETHOD(put_y)(THIS_ short newY);
    STDMETHOD(get_y)(THIS_ short FAR* retval);
    STDMETHOD(put_Position)(THIS_ IDualAutoClickPoint FAR* newPosition);
    STDMETHOD(get_Position)(THIS_ IDualAutoClickPoint FAR* FAR* retval);
    STDMETHOD(RefreshWindow)(THIS);
    STDMETHOD(SetAllProps)(THIS_ short x, short y, BSTR text);
    STDMETHOD(ShowWindow)(THIS);
END_DUAL_INTERFACE_PART(DualAClick)
```

Zur Verbindung mit der MFC-dualen Schnittstelle [QueryInterface](/windows/desktop/com/queryinterface--navigating-in-an-object) Mechanismus, Hinzufügen einer `INTERFACE_PART` einen Eintrag in die schnittstellenzuordnung:

```cpp
BEGIN_INTERFACE_MAP(CAutoClickDoc, CDocument)
    INTERFACE_PART(CAutoClickDoc, DIID_IAClick, Dispatch)
    INTERFACE_PART(CAutoClickDoc, IID_IDualAClick, DualAClick)
END_INTERFACE_MAP()
```

Als Nächstes müssen Sie in der Implementierung der Schnittstelle zu füllen. Zum größten Teil, Sie werden für die Delegierung an die vorhandene MFC-Bibliothek `IDispatch` Implementierung. Zum Beispiel:

```cpp
STDMETHODIMP_(ULONG) CAutoClickDoc::XDualAClick::AddRef()
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    return pThis->ExternalAddRef();
}

STDMETHODIMP_(ULONG) CAutoClickDoc::XDualAClick::Release()
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    return pThis->ExternalRelease();
}

STDMETHODIMP CAutoClickDoc::XDualAClick::QueryInterface(
    REFIID iid,
    LPVOID* ppvObj)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    return pThis->ExternalQueryInterface(&iid, ppvObj);
}

STDMETHODIMP CAutoClickDoc::XDualAClick::GetTypeInfoCount(
    UINT FAR* pctinfo)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);
    ASSERT(lpDispatch != NULL);
    return lpDispatch->GetTypeInfoCount(pctinfo);
}

STDMETHODIMP CAutoClickDoc::XDualAClick::GetTypeInfo(
    UINT itinfo,
    LCID lcid,
    ITypeInfo FAR* FAR* pptinfo)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);
    ASSERT(lpDispatch != NULL);

    return lpDispatch->GetTypeInfo(itinfo, lcid, pptinfo);
}

STDMETHODIMP CAutoClickDoc::XDualAClick::GetIDsOfNames(
    REFIID riid,
    OLECHAR FAR* FAR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID FAR* rgdispid)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);
    ASSERT(lpDispatch != NULL);

    return lpDispatch->GetIDsOfNames(riid, rgszNames, cNames, lcid, rgdispid);
}

STDMETHODIMP CAutoClickDoc::XDualAClick::Invoke(
    DISPID dispidMember,
    REFIID riid,
    LCID lcid,
    WORD wFlags,
    DISPPARAMS FAR* pdispparams,
    VARIANT FAR* pvarResult,
    EXCEPINFO FAR* pexcepinfo,
    UINT FAR* puArgErr)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);
    ASSERT(lpDispatch != NULL);

    return lpDispatch->Invoke(dispidMember, riid, lcid,
        wFlags, pdispparams, pvarResult, pexcepinfo, puArgErr);
}
```

Für Methoden und Accessorfunktionen der Eigenschaft des Objekts müssen Sie in der Implementierung zu füllen. Ihre Funktionen-Methode und Eigenschaft können in der Regel an die Methoden, die mithilfe der Klassen-Assistent generiert delegieren. Wenn Sie Eigenschaften festlegen, Variablen direkt zugreifen, müssen Sie jedoch den Code, um Get/Put von den Wert in die Variable zu schreiben. Zum Beispiel:

```cpp
STDMETHODIMP CAutoClickDoc::XDualAClick::put_text(BSTR newText)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    // MFC automatically converts from Unicode BSTR to
    // Ansi CString, if necessary...
    pThis->m_str = newText;
    return NOERROR;
}

STDMETHODIMP CAutoClickDoc::XDualAClick::get_text(BSTR* retval)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    // MFC automatically converts from Ansi CString to
    // Unicode BSTR, if necessary...
    pThis->m_str.SetSysString(retval);
    return NOERROR;
}
```

## <a name="passing-dual-interface-pointers"></a>Übergabe von duale Schnittstellen Zeigern

Übergeben den Mauszeiger duale Schnittstellen ist nicht einfach ist, insbesondere, wenn Sie aufrufen müssen `CCmdTarget::FromIDispatch`. `FromIDispatch` funktioniert nur auf MFC `IDispatch` Zeiger. Eine Möglichkeit zur Umgehung dieses Problems wird zum Abfragen von der ursprünglichen `IDispatch` Zeiger durchführen, indem Sie MFC und übergeben Sie diesen Zeiger an Funktionen, die ihn benötigen. Zum Beispiel:

```
STDMETHODIMP CAutoClickDoc::XDualAClick::put_Position(
    IDualAutoClickPoint FAR* newPosition)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    LPDISPATCH lpDisp = NULL;
    newPosition->QueryInterface(IID_IDispatch, (LPVOID*)&lpDisp);
    pThis->SetPosition(lpDisp);
    lpDisp->Release();
    return NOERROR;
}
```

Vor dem wieder über die duale Schnittstellen-Methode die Übergabe eines Zeigers, müssen Sie möglicherweise konvertieren in die MFC-Bibliothek `IDispatch` Zeiger auf Ihrem Dual-Schnittstellenzeiger. Zum Beispiel:

```
STDMETHODIMP CAutoClickDoc::XDualAClick::get_Position(
    IDualAutoClickPoint FAR* FAR* retval)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    LPDISPATCH lpDisp;
    lpDisp = pThis->GetPosition();
    lpDisp->QueryInterface(IID_IDualAutoClickPoint, (LPVOID*)retval);
    return NOERROR;
}
```

## <a name="registering-the-applications-type-library"></a>Beim Registrieren der Typbibliothek für der Anwendung

AppWizard generiert keinen Code aus, um eine Serveranwendung OLE-Automatisierung mit dem System registriert. Es gibt andere Möglichkeiten zum Registrieren der Typbibliothek, ist es sinnvoll, damit die Anwendung, die die Typbibliothek zu registrieren, wenn der OLE-Typinformationen, d. h. aktualisiert wird, wenn die Anwendung als eigenständige ausgeführt wird.

Zum Registrieren der Anwendung Typbibliothek, wenn die Anwendung ausgeführt wird eigenständig:

- Umfassen Sie AFXCTL an. H in Ihrem Standard umfasst Headerdatei STDAFX. H, die Definition der Zugriff auf die `AfxOleRegisterTypeLib` Funktion.

- In Ihrer Anwendungsverzeichnis `InitInstance` funktioniert, suchen Sie den Aufruf von `COleObjectFactory::UpdateRegistryAll`. Fügen Sie folgenden Aufruf wird einen Aufruf von `AfxOleRegisterTypeLib`unter Angabe der **LIBID** , Ihre Typbibliothek, zusammen mit dem Namen der Typbibliothek entsprechen:

    ```cpp
    // When a server application is launched stand-alone, it is a good idea
    // to update the system registry in case it has been damaged.
    m_server.UpdateRegistry(OAT_DISPATCH_OBJECT);

    COleObjectFactory::UpdateRegistryAll();

    // DUAL_SUPPORT_START
        // Make sure the type library is registered or dual interface won't work.
        AfxOleRegisterTypeLib(AfxGetInstanceHandle(),
            LIBID_ACDual,
            _T("AutoClik.TLB"));
    // DUAL_SUPPORT_END
    ```

## <a name="modifying-project-build-settings-to-accommodate-type-library-changes"></a>Ändern von Buildeinstellungen des Projekts um Type Library-Änderungen zu berücksichtigen.

So ändern Sie den Buildeinstellungen des Projekts, damit eine Header-Datei mit **UUID** Definitionen wird vom MkTypLib generiert, wenn die Typbibliothek neu erstellt wird:

1. Auf der **erstellen** Menü klicken Sie auf **Einstellungen**, und wählen Sie dann die ODL-Datei aus der Liste der Dateien für jede Konfiguration.

2. Klicken Sie auf die **OLE Typen** Registerkarte und geben Sie einen Dateinamen in der **Ausgabeheader** Feld "Filename". Verwenden Sie einen Dateinamen, der nicht bereits von Ihrem Projekt verwendet wird, da MkTypLib eine vorhandene Datei überschrieben werden. Klicken Sie auf **OK** schließen die **Buildeinstellungen** Dialogfeld.

Hinzufügen der **UUID** Definitionen aus der MkTypLib generierte Headerdatei zu Ihrem Projekt:

1. Enthalten die MkTypLib generierte Headerdatei in Ihrem Standard umfasst Headerdatei STDAFX. H.

2. Erstellen Sie eine neue Datei INITIIDS. CPP, und fügen sie Ihrem Projekt hinzu. Enthalten Sie in dieser Datei Ihrer MkTypLib generierter Header-Datei nach dem einschließen von OLE2. H und INITGUID. H:

    ```cpp
    // initIIDs.c: defines IIDs for dual interfaces
    // This must not be built with precompiled header.
    #include <ole2.h>
    #include <initguid.h>
    #include "acdual.h"
    ```

3. Auf der **erstellen** Menü klicken Sie auf **Einstellungen**, und wählen Sie dann auf INITIIDS. CPP aus der Liste der Dateien für jede Konfiguration.

4. Klicken Sie auf die **C++** Registerkarte, klicken Sie auf Kategorie **vorkompilierte Header**, und wählen Sie die **vorkompilierte Header nicht verwenden** Optionsfeld. Klicken Sie auf OK, um schließen die **Buildeinstellungen** Dialogfeld.

## <a name="specifying-the-correct-object-class-name-in-the-type-library"></a>Der Klassenname für die richtige Objekt angeben in der Typbibliothek

Die Assistenten, die im Lieferumfang von Visual C++ nicht ordnungsgemäß verwenden den Klassennamen für die Implementierung die Co-Klasse in ODL-Datei für die OLE-erstellbaren Klassen des Servers angeben. Dies funktioniert, ist der Klassenname für die Implementierung wahrscheinlich nicht den Klassennamen, die Benutzern des Objekts verwendet werden sollen. Geben Sie den richtigen Namen, öffnen Sie die ODL-Datei, suchen Sie nach jeder Anweisung Co-Klasse, und ersetzen den Klassennamen für die Implementierung, mit dem richtigen Namen für die externe.

Beachten Sie, dass bei die Co-Klasse-Anweisung geändert werden, werden die Namen der **CLSID**s in der MkTypLib generierte Headerdatei ändert sich entsprechend. Sie müssen Ihren Code, um die neuen Variablennamen verwenden, zu aktualisieren.

## <a name="handling-exceptions-and-the-automation-error-interfaces"></a>Behandeln von Ausnahmen und die Automatisierungsschnittstellen für Fehler

Des Automatisierungsobjekts Methoden und Accessorfunktionen der Eigenschaft möglicherweise Ausnahmen auslösen. Falls Ja, Sie in Ihrer Implementierung duale Schnittstellen werden behandelt sollte, und übergeben von Informationen über die Ausnahme zurück an den Controller über die Benutzeroberfläche des OLE-Automatisierung für die Fehlerbehandlung, `IErrorInfo`. Diese Schnittstelle bietet Informationen über beide-ausführlicher, kontextbezogener Fehler `IDispatch` und VTBL-Schnittstellen. Um anzugeben, dass ein Fehlerhandler verfügbar ist, sollten Sie implementieren die `ISupportErrorInfo` Schnittstelle.

Um den Fehlerbehandlungsmechanismus zu veranschaulichen, wird davon ausgegangen Sie, dass die Klassen-Assistenten generierte Funktionen verwendet, um die standardmäßigen Dispatch-Unterstützung implementieren Ausnahmen auslösen. Die Implementierung von MFC `IDispatch::Invoke` in der Regel diese Ausnahmen abfängt und wandelt sie in einer EXCEPTINFO-Struktur, die über zurückgegeben wird das `Invoke` aufrufen. Wenn VTBL-Schnittstelle verwendet wird, sind Sie jedoch zum Abfangen von Ausnahmen selbst verantwortlich. Als Beispiel für die duale Schnittstellen Methoden schützen:

```cpp
STDMETHODIMP CAutoClickDoc::XDualAClick::put_text(BSTR newText)
{
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)
    TRY_DUAL(IID_IDualAClick)
    {
        // MFC automatically converts from Unicode BSTR to
        // Ansi CString, if necessary...
        pThis->m_str = newText;
        return NOERROR;
    }
    CATCH_ALL_DUAL
}
```

`CATCH_ALL_DUAL` übernimmt den richtigen Fehlercode zurückgeben, wenn eine Ausnahme auftritt. `CATCH_ALL_DUAL` Konvertiert eine MFC-Ausnahme in der OLE-Automatisierung für die Fehlerbehandlung mithilfe der `ICreateErrorInfo` Schnittstelle. (Ein Beispiel für `CATCH_ALL_DUAL` Makro ist in der Datei MFCDUAL. H in die [ACDUAL](../visual-cpp-samples.md) Beispiel. Die Funktion, die sie zur Ausnahmebehandlung ruft `DualHandleException`, in der Datei MFCDUAL ist. CPP.) `CATCH_ALL_DUAL` bestimmt den Fehlercode basierend auf den Typ der Ausnahme zurückgegeben, die aufgetreten sind:

- [COleDispatchException](../mfc/reference/coledispatchexception-class.md) – In diesem Fall `HRESULT` erstellt wird, mit dem folgenden Code:

    ```cpp
    hr = MAKE_HRESULT(SEVERITY_ERROR, FACILITY_ITF, (e->m_wCode + 0x200));
    ```

     Dies erstellt eine `HRESULT` speziell für die Schnittstelle, die die Ausnahme verursacht hat. Der Fehlercode versetzt wird, von 0 x 200, um Konflikte mit den systemdefinierten zu vermeiden `HRESULT`s für die standard-OLE-Schnittstellen.

- [CMemoryException](../mfc/reference/cmemoryexception-class.md) – In diesem Fall `E_OUTOFMEMORY` zurückgegeben wird.

- Alle anderen Ausnahmen – In diesem Fall `E_UNEXPECTED` zurückgegeben wird.

Um anzugeben, dass der OLE-Automatisierung Fehlerhandler wird verwendet, sollten Sie auch implementieren die `ISupportErrorInfo` Schnittstelle.

Fügen Sie zunächst Code auf Ihre Klassendefinition Automation, um anzuzeigen, er unterstützt `ISupportErrorInfo`.

Anschließend fügen Sie Code, um die schnittstellenzuordnung für Ihre Automatisierungsklasse Zuordnen der `ISupportErrorInfo` Implementierungsklasse mit MFC `QueryInterface` Mechanismus. Die `INTERFACE_PART` Anweisung entspricht der Klasse definiert für `ISupportErrorInfo`.

Abschließend implementieren Sie die Klasse, die definiert, die zur Unterstützung von `ISupportErrorInfo`.

(Die [ACDUAL](../visual-cpp-samples.md) Beispiel enthält drei Makros können diese drei Schritte ausführen, `DECLARE_DUAL_ERRORINFO`, `DUAL_ERRORINFO_PART`, und `IMPLEMENT_DUAL_ERRORINFO`, alle in MFCDUAL enthalten. H.)

Das folgende Beispiel implementiert eine Klasse, die zur Unterstützung von definiert `ISupportErrorInfo`. `CAutoClickDoc` Der Name Ihrer Automation-Klasse und `IID_IDualAClick` ist die **IID** für die Schnittstelle, die die Quelle von Fehlern, die durch die OLE-Automatisierungsobjekte Error-Objekt gemeldet wurde:

```cpp
STDMETHODIMP_(ULONG) CAutoClickDoc::XSupportErrorInfo::AddRef()
{
    METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)
    return pThis->ExternalAddRef();
}

STDMETHODIMP_(ULONG) CAutoClickDoc::XSupportErrorInfo::Release()
{
    METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)
    return pThis->ExternalRelease();
}

STDMETHODIMP CAutoClickDoc::XSupportErrorInfo::QueryInterface(
    REFIID iid,
    LPVOID* ppvObj)
{
    METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)
    return pThis->ExternalQueryInterface(&iid, ppvObj);
}

STDMETHODIMP CAutoClickDoc::XSupportErrorInfo::InterfaceSupportsErrorInfo(
    REFIID iid)
{
    METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)
    return (iid == IID_IDualAClick) S_OK : S_FALSE;
}
```

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
