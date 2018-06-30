---
title: 'TN065: Unterstützung für duale Schnittstellen für OLE-Automatisierungsserver | Microsoft Docs'
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
ms.openlocfilehash: e30be46aeab92f63f1b4cba593cda52bf9aeef9a
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122182"
---
# <a name="tn065-dual-interface-support-for-ole-automation-servers"></a>TN065: Unterstützung für duale Schnittstellen für OLE-Automatisierungsserver

> [!NOTE]
> Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

Dieser Hinweis erläutert, wie eine Anwendung mit OLE-Automatisierungsserver MFC-basierte Unterstützung für duale Schnittstellen hinzu. Die [ACDUAL](../visual-cpp-samples.md) Beispiel veranschaulicht wird die Unterstützung für duale Schnittstellen und der Beispielcode in diesem Hinweis ACDUAL entnommen. Die Makros, die in diesem Hinweis, z. B. DECLARE_DUAL_ERRORINFO, DUAL_ERRORINFO_PART und IMPLEMENT_DUAL_ERRORINFO, beschrieben sind Teil der ACDUAL-Beispiel und in MFCDUAL gefunden werden können. H.

## <a name="dual-interfaces"></a>Duale Schnittstellen

OLE-Automatisierung können Sie implementieren eine `IDispatch` -Schnittstelle, eine VTBL-Schnittstelle oder eine duale Schnittstelle (umfasst sowohl), empfiehlt Microsoft dringend, dass Sie für alle OLE-Automatisierungsobjekte verfügbar gemachte duale Schnittstellen implementieren. Duale Schnittstellen haben erhebliche Vorteile gegenüber `IDispatch`- oder nur VTBL-Schnittstellen:

- Bindung kann zur Kompilierzeit über die VTBL-Schnittstelle, oder stattfinden zur Laufzeit über `IDispatch`.

- OLE-Automatisierungscontroller, die den VTBL-Schnittstelle verwenden, können möglicherweise von einer verbesserten Leistung profitieren.

- Vorhandenen OLE-Automatisierungscontroller, mit denen die `IDispatch` Schnittstelle sind weiterhin funktionsfähig.

- Die VTBL-Schnittstelle ist einfacher, die von C++ aus aufzurufen.

- Duale Schnittstellen sind erforderlich, um die Kompatibilität mit Funktionen zur Unterstützung von Visual Basic-Objekt.

## <a name="adding-dual-interface-support-to-a-ccmdtarget-based-class"></a>Hinzufügen von Unterstützung für duale zu einer basierende CCmdTarget-Klasse

Eine duale Schnittstelle ist genau genommen nur eine benutzerdefinierte Schnittstelle abgeleitet `IDispatch`. Die einfachste Möglichkeit zum Implementieren der Unterstützung für duale Schnittstellen in einem `CCmdTarget`-Basis-Klasse wird zum ersten implementieren die normale Verteilung-Schnittstelle für die Klasse, die mithilfe von MFC und ClassWizard, und klicken Sie dann die benutzerdefinierte Schnittstelle später hinzufügen. Ihre benutzerdefinierte Implementierung wird größtenteils, einfach delegieren, zurück an die MFC-Bibliothek `IDispatch` Implementierung.

Ändern Sie zunächst ODL-Datei für Ihren Server duale Schnittstellen für die Objekte zu definieren. Um eine duale Schnittstelle zu definieren, müssen Sie eine Interface-Anweisung verwenden, statt die `DISPINTERFACE` -Anweisung, die Visual C++-Assistenten generieren. Anstatt zu entfernen, die vorhandene `DISPINTERFACE` -Anweisung, fügen Sie eine neue Schnittstelle-Anweisung hinzu. Durch Beibehalten der `DISPINTERFACE` Formular können Sie weiterhin ClassWizard zu verwenden, um Eigenschaften und Methoden für Ihr Objekt hinzuzufügen, aber Sie müssen die entsprechenden Eigenschaften und Methoden Interface-Anweisung hinzufügen.

Eine Schnittstelle-Anweisung für eine duale Schnittstelle benötigen die *OLEAUTOMATION* und *DUALE* Attribute und die Schnittstelle muss von abgeleitet werden `IDispatch`. Können Sie die [GUIDGEN](../visual-cpp-samples.md) -Beispiel zum Erstellen einer **IID** für die duale Schnittstelle:

```IDL
[ uuid(0BDD0E81-0DD7-11cf-BBA8-444553540000), // IID_IDualAClick
    oleautomation,
    dual
]
interface IDualAClick : IDispatch
    {
    };
```

Sobald Sie die Interface-Anweisung vorbereitet haben, starten Sie die Einträge für die Methoden und Eigenschaften hinzufügt. Für duale Schnittstellen müssen Sie die Parameterlisten neu anordnen, dass die Methoden und die Eigenschaft Accessor-Funktionen in der dualen Schnittstelle zurückgeben einer **HRESULT** und die Rückgabewerte übergeben, als Parameter mit den Attributen `[retval,out]`. Denken Sie daran, dass für Eigenschaften, Sie benötigen beide einen Lesevorgang hinzufügen (`propget`) und Schreiben (`propput`) Zugriff auf die Funktion mit der gleichen Id. Zum Beispiel:

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

Sobald die ODL-Datei aktualisiert wurde, mit der schnittstellenzuordnungsmechanismus von MFC definieren eine Implementierungsklasse für die duale Schnittstelle in der Objektklasse, und stellen die entsprechenden Einträge in MFC `QueryInterface` Mechanismus. Sie benötigen einen Eintrag in der `INTERFACE_PART` Block für jeden Eintrag in der Schnittstelle-Anweisung die ODL plus die Einträge für eine Dispatch-Schnittstelle. Jeder ODL-Eintrag mit dem *Propput* Attribut benötigt eine Funktion namens `put_propertyname`. Jeder Eintrag mit dem *Propget* Attribut benötigt eine Funktion namens `get_propertyname`.

Um eine Implementierungsklasse für die duale Schnittstelle zu definieren, fügen einen `DUAL_INTERFACE_PART` Block auf Ihre Objektklassendefinition. Zum Beispiel:

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

Zur Verbindung mit der MFC-dualen Schnittstelle [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms687230) Mechanismus, Hinzufügen einer `INTERFACE_PART` Eintrag, um die schnittstellenzuordnung:

```cpp
BEGIN_INTERFACE_MAP(CAutoClickDoc, CDocument)
    INTERFACE_PART(CAutoClickDoc, DIID_IAClick, Dispatch)
    INTERFACE_PART(CAutoClickDoc, IID_IDualAClick, DualAClick)
END_INTERFACE_MAP()
```

Als Nächstes müssen Sie in der Implementierung der Schnittstelle zu füllen. Meistens, Sie werden für die Delegierung an die MFC-Bibliothek vorhandene `IDispatch` Implementierung. Zum Beispiel:

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

Für Methoden und Accessorfunktionen der Eigenschaft des Objekts müssen Sie in der Implementierung zu füllen. Methoden- und Funktionen können in der Regel an die Methoden, die mithilfe der Klassen-Assistent generiert delegieren. Wenn Sie Eigenschaften direkt den Zugriff auf Variablen einrichten, müssen Sie jedoch den Code, um Get/Put von den Wert in die Variable zu schreiben. Zum Beispiel:

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

## <a name="passing-dual-interface-pointers"></a>Übergabe von Zeigern duale Schnittstellen

Die duale Zeiger übergeben, ist nicht einfach, insbesondere, wenn Sie aufrufen müssen `CCmdTarget::FromIDispatch`. `FromIDispatch` funktioniert nur auf MFC `IDispatch` Zeiger. Eine Möglichkeit zum Umgehen dieses Problems ist für die ursprüngliche Abfrage `IDispatch` Zeiger Satz von MFC einrichten, und übergeben Sie diesen Zeiger an Funktionen, die sie benötigen. Zum Beispiel:

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

Vor der Übergabe eines Zeigers wieder über die duale-Methode, müssen sie über die MFC-Bibliothek zu konvertieren `IDispatch` Zeiger auf die Dual-Schnittstellenzeiger auf. Zum Beispiel:

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

## <a name="registering-the-applications-type-library"></a>Beim Registrieren der Typbibliothek für die Anwendung

AppWizard generiert keinen Code aus, um die Typbibliothek für ein OLE-Automatisierung Server-Anwendung mit dem System zu registrieren. Dafür gibt es weitere Möglichkeiten zum Registrieren der Typbibliothek, empfiehlt es sich, dass die Anwendung die Typbibliothek zu registrieren, wenn die OLE-Typinformationen, also aktualisiert wird, wenn die Anwendung eigenständigen ausgeführt wird.

Zum Registrieren der Anwendung Typbibliothek, wenn die Anwendung ausgeführt wird eigenständig:

- AFXCTL einschließen H in Ihrem Standard umfasst Headerdatei STDAFX. H, die Definition der Zugriff auf die `AfxOleRegisterTypeLib` Funktion.

- In der Anwendungsverzeichnis `InitInstance` funktionieren, suchen Sie den Aufruf von `COleObjectFactory::UpdateRegistryAll`. Fügen Sie nach diesem Aufruf einen Aufruf von `AfxOleRegisterTypeLib`unter Angabe der **LIBID** , die Typbibliothek, zusammen mit dem Namen der Typbibliothek entspricht:

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

Zum Ändern der Buildeinstellungen des Projekts, damit ein Header mit **UUID** Definitionen von MkTypLib generiert, sobald die Typbibliothek neu erstellt wird:

1. Auf der **erstellen** Menü klicken Sie auf **Einstellungen**, und wählen Sie dann die ODL-Datei in der Dateiliste für jede Konfiguration.

2. Klicken Sie auf die **OLE Typen** Registerkarte und geben Sie einen Dateinamen in der **Ausgabeheader** Filename-Feld. Verwenden Sie ein Dateiname, der vom das Projekt nicht bereits verwendet wird, da MkTypLib eine vorhandene Datei überschrieben werden. Klicken Sie auf **OK** schließen die **Buildeinstellungen** (Dialogfeld).

Hinzufügen der **UUID** Definitionen über die MkTypLib generierte Headerdatei zu Ihrem Projekt:

1. Enthalten die MkTypLib generierte Headerdatei in Ihrer standardmäßigen enthält Headerdatei STDAFX. H.

2. Erstellen Sie eine neue Datei INITIIDS. CPP, und fügen sie Ihrem Projekt hinzu. In dieser Datei wird schließen Sie der MkTypLib generierte Headerdatei nach einschließlich OLE2 ein. H und INITGUID. H

    ```cpp
    // initIIDs.c: defines IIDs for dual interfaces
    // This must not be built with precompiled header.
    #include <ole2.h>
    #include <initguid.h>
    #include "acdual.h"
    ```

3. Auf der **erstellen** Menü klicken Sie auf **Einstellungen**, und wählen Sie dann INITIIDS. CPP in der Dateiliste für jede Konfiguration.

4. Klicken Sie auf die **C++** Registerkarte, klicken Sie auf Kategorie **vorkompilierte Header**, und wählen Sie die **vorkompilierte Header nicht verwenden** Optionsfeld. Klicken Sie auf OK, um das Schließen der **Buildeinstellungen** (Dialogfeld).

## <a name="specifying-the-correct-object-class-name-in-the-type-library"></a>Angeben der richtigen Objektnamen für die Klasse in der Typbibliothek

Die Assistenten, die im Lieferumfang von Visual C++ nicht ordnungsgemäß mithilfe der Klassenname für die Implementierung an die Co-Klasse in der Server ODL-Datei für OLE-erstellbaren Klassen. Während dies funktioniert, ist der Klassenname für die Implementierung wahrscheinlich nicht den Klassennamen, die Benutzern des Objekts verwendet werden soll. Geben Sie den richtigen Namen, öffnen Sie die ODL-Datei, suchen Sie nach jeder Anweisung Co-Klasse, und ersetzen den Klassennamen für die Implementierung mit dem richtigen externen Namen.

Beachten Sie, dass, wenn die Coclass-Anweisung geändert wird, wird die Variablennamen des **CLSID**s in der MkTypLib generierte Headerdatei ändert sich entsprechend. Sie müssen den Code verwenden Sie den neuen Namen aktualisieren.

## <a name="handling-exceptions-and-the-automation-error-interfaces"></a>Behandeln von Ausnahmen und die Automatisierungsschnittstellen Fehler

Des Automatisierungsobjekts Methoden und Accessorfunktionen der Eigenschaft möglicherweise Ausnahmen ausgelöst. Wenn also in Ihrer Implementierung der dualen Schnittstellen zu behandeln und Informationen zur Ausnahme wieder an den Controller über die OLE-Automatisierung Fehlerbehandlungs-Schnittstelle, übergeben werden soll `IErrorInfo`. Diese Schnittstelle bietet detaillierte, kontextbezogene Informationen über beide `IDispatch` und VTBL-Schnittstellen. Um anzugeben, dass kein Fehlerhandler verfügbar ist, implementieren Sie die `ISupportErrorInfo` Schnittstelle.

Um die Fehlerbehandlungsmechanismus zu veranschaulichen, wird davon ausgegangen Sie, dass die Klassen-Assistenten generierte Funktionen verwendet, um die standard-Dispatch-Unterstützung implementieren Ausnahmen auslöst. Die Implementierung von MFC `IDispatch::Invoke` in der Regel fängt diese Ausnahmen ab und wandelt sie in einer EXCEPTINFO-Struktur, die über zurückgegeben wird die `Invoke` aufrufen. Wenn VTBL-Schnittstelle verwendet wird, sind Sie jedoch zum Abfangen von Ausnahmen selbst verantwortlich. Als Beispiel für den Schutz Ihrer Dual-Schnittstellenmethoden:

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

`CATCH_ALL_DUAL` übernimmt den richtigen Fehlercode zurückgeben, wenn eine Ausnahme auftritt. `CATCH_ALL_DUAL` Konvertiert eine MFC-Ausnahme in der OLE-Automatisierung Fehlerbehandlungs-Informationen mithilfe der `ICreateErrorInfo` Schnittstelle. (Ein Beispiel für `CATCH_ALL_DUAL` -Makro ist in der Datei MFCDUAL. H in der [ACDUAL](../visual-cpp-samples.md) Beispiel. Die Funktion, die sie behandeln von Ausnahmen, ruft `DualHandleException`, in der Datei MFCDUAL ist. CPP.) `CATCH_ALL_DUAL` bestimmt den Fehlercode, basierend auf den Typ der Ausnahme zurück, die vorgenommen:

- [COleDispatchException](../mfc/reference/coledispatchexception-class.md) – In diesem Fall `HRESULT` erstellt wird, mit dem folgenden Code:

    ```cpp
    hr = MAKE_HRESULT(SEVERITY_ERROR, FACILITY_ITF, (e->m_wCode + 0x200));
    ```

     Dies erstellt eine `HRESULT` speziell für die Schnittstelle, die die Ausnahme verursacht hat. Der Fehlercode von 0 x 200 Konflikte mit den systemdefinierten versetzt wird `HRESULT`s für standard OLE-Schnittstellen.

- [CMemoryException](../mfc/reference/cmemoryexception-class.md) – In diesem Fall `E_OUTOFMEMORY` zurückgegeben wird.

- Alle anderen Ausnahmen – In diesem Fall `E_UNEXPECTED` zurückgegeben wird.

Um anzugeben, dass der OLE-Automatisierung Fehlerhandler verwendet wird, sollten Sie auch implementieren die `ISupportErrorInfo` Schnittstelle.

Fügen Sie Code zunächst auf Ihre Klassendefinition Automation anzuzeigende unterstützt `ISupportErrorInfo`.

Zweitens, fügen Sie Code auf Ihre Automatisierungsklasse schnittstellenzuordnung Zuordnen der `ISupportErrorInfo` Implementierungsklasse mit MFC `QueryInterface` Mechanismus. Die `INTERFACE_PART` Anweisung entspricht der Klasse definiert für `ISupportErrorInfo`.

Abschließend implementieren die Klasse definiert, die zur Unterstützung von `ISupportErrorInfo`.

(Die [ACDUAL](../visual-cpp-samples.md) Beispiel enthält drei Makros, damit diese drei Schritte ausgeführt werden können `DECLARE_DUAL_ERRORINFO`, `DUAL_ERRORINFO_PART`, und `IMPLEMENT_DUAL_ERRORINFO`, alle in MFCDUAL enthalten. H.)

Das folgende Beispiel implementiert eine Klasse, die zur Unterstützung von definiert `ISupportErrorInfo`. `CAutoClickDoc` Der Name der Automatisierungsklasse und `IID_IDualAClick` ist die **IID** für die Schnittstelle, die die Ursache der Fehler, die über die OLE-Automatisierung Error-Objekt gemeldet wird:

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

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)  
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)  
