---
title: 'TN065: Unterstützung für die duale Schnittstelle für OLE-Automatisierungsserver'
ms.date: 06/28/2018
f1_keywords:
- vc.ole
helpviewer_keywords:
- dual interfaces [MFC], OLE Automation
- TN065 [MFC]
- ACDUAL sample [MFC]
- Automation servers [MFC], dual-interface support
ms.assetid: b5c8ed09-2f7f-483c-80fc-2a47ad896063
ms.openlocfilehash: afcbfd643d8b931e61b0f011b66482be5b2bcc82
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510998"
---
# <a name="tn065-dual-interface-support-for-ole-automation-servers"></a>TN065: Unterstützung für die duale Schnittstelle für OLE-Automatisierungsserver

> [!NOTE]
> Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

In diesem Hinweis wird erläutert, wie einer MFC-basierten OLE-Automatisierungsserver Anwendung eine Dual-Interface-Unterstützung hinzugefügt wird. Das [ACDual](../overview/visual-cpp-samples.md) -Beispiel veranschaulicht die Unterstützung für duale Schnittstellen, und der Beispielcode in dieser Notiz wird aus dem ACDual entnommen. Die in dieser Notiz beschriebenen Makros, wie z. b. DECLARE_DUAL_ERRORINFO, DUAL_ERRORINFO_PART und IMPLEMENT_DUAL_ERRORINFO, sind Teil des ACDual-Beispiels und können in mfcdual gefunden werden. Micha.

## <a name="dual-interfaces"></a>Duale Schnittstellen

Obwohl die OLE-Automatisierung es Ihnen ermöglicht `IDispatch` , eine Schnittstelle, eine VTBL-Schnittstelle oder eine duale Schnittstelle (die beide umfasst) zu implementieren, empfiehlt Microsoft dringend, duale Schnittstellen für alle verfügbar gemachten OLE-Automatisierungs Objekte zu implementieren. Duale Schnittstellen haben bedeutende Vorteile `IDispatch`gegenüber reinen oder VTBL-Schnittstellen:

- Die Bindung kann zur Kompilierzeit über die VTBL-Schnittstelle oder zur Laufzeit durch `IDispatch`geführt werden.

- OLE-Automatisierungs Controller, die die VTBL-Schnittstelle verwenden können, können von einer verbesserten Leistung profitieren.

- Vorhandene OLE-Automatisierungs Controller, die `IDispatch` die-Schnittstelle verwenden, funktionieren weiterhin.

- Die VTBL-Schnittstelle kann einfacher aus C++aufgerufen werden.

- Duale Schnittstellen sind erforderlich, um die Kompatibilität mit Visual Basic Objekt-Unterstützungsfunktionen zu unterstützen

## <a name="adding-dual-interface-support-to-a-ccmdtarget-based-class"></a>Hinzufügen von Unterstützung für duale Schnittstellen zu einer CCmdTarget-basierten Klasse

Eine duale Schnittstelle ist wirklich nur eine benutzerdefinierte Schnitt `IDispatch`Stelle, die von abgeleitet ist. Die einfachste Möglichkeit, die Unterstützung für duale Schnittstellen in `CCmdTarget`einer-basierten Klasse zu implementieren, besteht darin, zuerst mithilfe von MFC und ClassWizard die normale Dispatch-Schnittstelle für Ihre Klasse zu implementieren und die benutzerdefinierte Schnittstelle später hinzuzufügen. Zum größten Teil wird die Implementierung der benutzerdefinierten Schnittstelle einfach an die MFC `IDispatch` -Implementierung delegiert.

Ändern Sie zunächst die ODL-Datei für Ihren Server, um duale Schnittstellen für die Objekte zu definieren. Um eine duale Schnittstelle zu definieren, müssen Sie anstelle der `DISPINTERFACE` von den visuellen C++ Assistenten generierten Anweisung eine Interface-Anweisung verwenden. Anstatt die vorhandene `DISPINTERFACE` -Anweisung zu entfernen, fügen Sie eine neue Interface-Anweisung hinzu. Wenn Sie das `DISPINTERFACE` Formular beibehalten, können Sie den Klassen-Assistenten weiterhin zum Hinzufügen von Eigenschaften und Methoden zu Ihrem Objekt verwenden, aber Sie müssen der Schnittstellen Anweisung die entsprechenden Eigenschaften und Methoden hinzufügen.

Eine Interface-Anweisung für eine duale Schnittstelle muss über die *oleautomation* -und *Dual* -Attribute verfügen, und die `IDispatch`-Schnittstelle muss von abgeleitet werden. Sie können das [GUIDGEN](../overview/visual-cpp-samples.md) -Beispiel verwenden, um eine **IID** für die duale Schnittstelle zu erstellen:

```IDL
[ uuid(0BDD0E81-0DD7-11cf-BBA8-444553540000), // IID_IDualAClick
    oleautomation,
    dual
]
interface IDualAClick : IDispatch
    {
    };
```

Nachdem Sie die Interface-Anweisung eingerichtet haben, beginnen Sie mit dem Hinzufügen von Einträgen für die Methoden und Eigenschaften. Für duale Schnittstellen müssen Sie die Parameterlisten neu anordnen, damit die Methoden und Eigenschaften Accessor-Funktionen in der Dual-Schnittstelle ein **HRESULT** zurückgeben und ihre Rückgabewerte als Parameter `[retval,out]`mit den Attributen übergeben. Beachten Sie, dass Sie für-Eigenschaften sowohl eine Read (`propget`)-als auch eine Write (`propput`)-Zugriffs Funktion mit der gleichen ID hinzufügen müssen. Beispiel:

```IDL
[propput, id(1)] HRESULT text([in] BSTR newText);
[propget, id(1)] HRESULT text([out, retval] BSTR* retval);
```

Nachdem Sie die Methoden und Eigenschaften definiert haben, müssen Sie in ihrer Co-Klasse-Anweisung einen Verweis auf die Interface-Anweisung hinzufügen. Beispiel:

```IDL
[ uuid(4B115281-32F0-11cf-AC85-444553540000) ]
coclass Document
{
    dispinterface IAClick;
    [default] interface IDualAClick;
};
```

Nachdem die ODL-Datei aktualisiert wurde, verwenden Sie den Schnittstellen Zuordnungs Mechanismus von MFC, um eine Implementierungs Klasse für die duale Schnittstelle in der Objektklasse zu definieren und die entsprechenden `QueryInterface` Einträge im MFC-Mechanismus zu erstellen. Sie benötigen einen Eintrag im `INTERFACE_PART` -Block für jeden Eintrag in der Interface-Anweisung der ODL sowie die Einträge für eine Dispatch-Schnittstelle. Jeder ODL-Eintrag mit dem *PROPPUT* -Attribut benötigt eine `put_propertyname`Funktion mit dem Namen. Jeder Eintrag mit dem *propget* -Attribut benötigt eine Funktion `get_propertyname`mit dem Namen.

Fügen Sie der Objektklassen Definition einen `DUAL_INTERFACE_PART` -Block hinzu, um eine Implementierungs Klasse für die duale Schnittstelle zu definieren. Beispiel:

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

Fügen Sie der Schnittstellen Zuordnung einen `INTERFACE_PART` Eintrag hinzu, um die duale Schnittstelle mit dem MFC- [QueryInterface](/windows/win32/com/queryinterface--navigating-in-an-object) -Mechanismus zu verbinden:

```cpp
BEGIN_INTERFACE_MAP(CAutoClickDoc, CDocument)
    INTERFACE_PART(CAutoClickDoc, DIID_IAClick, Dispatch)
    INTERFACE_PART(CAutoClickDoc, IID_IDualAClick, DualAClick)
END_INTERFACE_MAP()
```

Als nächstes müssen Sie die Implementierung der-Schnittstelle ausfüllen. Zum größten Teil können Sie an die vorhandene MFC `IDispatch` -Implementierung delegieren. Beispiel:

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

Für die Methoden-und eigenschaftenaccessorfunktionen des-Objekts müssen Sie die-Implementierung ausfüllen. Die Methoden-und Eigenschafts Funktionen können im allgemeinen zurück an die mit ClassWizard generierten Methoden delegiert werden. Wenn Sie jedoch Eigenschaften so einrichten, dass direkt auf Variablen zugegriffen wird, müssen Sie den Code schreiben, um den Wert in der Variablen zu erhalten/zu platzieren. Beispiel:

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

## <a name="passing-dual-interface-pointers"></a>Übergeben von Dual-Interface-Zeigern

Das Übergeben des zweifach Schnittstellen Zeigers ist nicht ganz einfach, insbesondere dann `CCmdTarget::FromIDispatch`, wenn Sie anrufen müssen. `FromIDispatch`funktioniert nur mit den MFC `IDispatch` -Zeigern. Eine Möglichkeit, dieses Problem zu umgehen, besteht darin, den `IDispatch` von MFC eingerichteten ursprünglichen Zeiger abzufragen und diesen Zeiger an Funktionen zu übergeben, die ihn benötigen. Beispiel:

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

Vor der Übergabe eines Zeigers über die Dual-Interface-Methode müssen Sie ihn möglicherweise vom MFC `IDispatch` -Zeiger auf den Dual-Interface-Zeiger konvertieren. Beispiel:

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

## <a name="registering-the-applications-type-library"></a>Registrieren der Typbibliothek der Anwendung

Der AppWizard generiert keinen Code, um die Typbibliothek einer OLE-Automatisierungsserver Anwendung beim System zu registrieren. Es gibt zwar andere Möglichkeiten, die Typbibliothek zu registrieren, aber es ist praktisch, dass die Anwendung die Typbibliothek beim Aktualisieren der OLE-Typinformationen registriert, d. h. wenn die Anwendung eigenständig ausgeführt wird.

So registrieren Sie die Typbibliothek der Anwendung immer dann, wenn die Anwendung ausgeführt wird:

- Einschließen von afxctl. H in Ihrer Standard-enthält Header Datei stdafx. H, um auf die Definition der `AfxOleRegisterTypeLib` Funktion zuzugreifen.

- Suchen Sie in der `InitInstance` -Funktion Ihrer Anwendung den `COleObjectFactory::UpdateRegistryAll`-Befehl. Fügen Sie nach diesem-Befehl einen `AfxOleRegisterTypeLib`-Befehl hinzu, und geben Sie dabei die **LIBID** , die ihrer Typbibliothek entspricht, sowie den Namen der Typbibliothek an:

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

## <a name="modifying-project-build-settings-to-accommodate-type-library-changes"></a>Ändern von Projektbuildeinstellungen, um Änderungen an Typbibliotheken zu ermöglichen

Um die Buildeinstellungen eines Projekts so zu ändern, dass eine Header Datei mit **UUID** -Definitionen immer dann von MkTypLib generiert wird, wenn die Typbibliothek neu erstellt wird:

1. Klicken Sie im Menü **Erstellen** auf **Einstellungen**, und wählen Sie dann in der Datei Liste für jede Konfiguration die ODL-Datei aus.

2. Klicken Sie auf die Registerkarte **OLE Types** , und geben Sie einen Dateinamen im Feld Name des **Ausgabe Headers** an. Verwenden Sie einen Dateinamen, der nicht bereits von Ihrem Projekt verwendet wird, da MkTypLib jede vorhandene Datei überschreibt. Klicken Sie auf **OK** , um das Dialogfeld Buildeinstellungen zu schließen.

So fügen Sie dem Projekt die **UUID** -Definitionen aus der von MkTypLib generierten Header Datei hinzu:

1. Fügen Sie die von MkTypLib generierte Header Datei in die Standard Header Datei stdafx ein. Micha.

2. Erstellen Sie eine neue Datei, initiids. Cpp, und fügen Sie es dem Projekt hinzu. Fügen Sie in dieser Datei die MkTypLib-generierte Header Datei nach dem einschließen von OLE2 ein. H und Initguid. Micha

    ```cpp
    // initIIDs.c: defines IIDs for dual interfaces
    // This must not be built with precompiled header.
    #include <ole2.h>
    #include <initguid.h>
    #include "acdual.h"
    ```

3. Klicken Sie im Menü **Erstellen** auf **Einstellungen**, und wählen Sie dann initiids aus. Cpp in der Datei Liste für jede Konfiguration.

4. Klicken Sie **C++** auf die Registerkarte, klicken Sie auf Kategorie **Vorkompilierte Header**, und aktivieren Sie das Optionsfeld **nicht verwendete vorkompilierte Header** . Klicken Sie auf OK, um das Dialogfeld Buildeinstellungen zu schließen.

## <a name="specifying-the-correct-object-class-name-in-the-type-library"></a>Angeben des richtigen Objektklassen namens in der Typbibliothek

Die im visuellen C++ Element enthaltenen Assistenten verwenden den Implementierungsklassen Namen, um die Co-Klasse in der ODL-Datei des Servers für OLE-Erstell Bare Klassen anzugeben. Obwohl dies funktioniert, ist der Name der Implementierungs Klasse wahrscheinlich nicht der Klassenname, den Benutzer Ihres Objekts verwenden möchten. Um den richtigen Namen anzugeben, öffnen Sie die ODL-Datei, suchen Sie jede Co-Klasse-Anweisung, und ersetzen Sie den Namen der Implementierungs Klasse durch den korrekten externen Namen.

Beachten Sie Folgendes: Wenn die Co-Klasse-Anweisung geändert wird, ändern sich die Variablennamen von **CLSID**s in der von MkTypLib generierten Header Datei entsprechend. Sie müssen Ihren Code aktualisieren, damit die neuen Variablennamen verwendet werden.

## <a name="handling-exceptions-and-the-automation-error-interfaces"></a>Behandeln von Ausnahmen und Automatisierungs Fehler Schnittstellen

Die Methoden und Eigenschaften Accessor-Funktionen Ihres Automation-Objekts können Ausnahmen auslösen. Wenn dies der Fall ist, sollten Sie Sie in der Dual-Interface-Implementierung behandeln und Informationen über die Ausnahme an den Controller über die OLE-Automatisierungs-Schnitt `IErrorInfo`Stelle für die Fehlerbehandlung übergeben. Diese Schnittstelle bietet ausführliche, kontextabhängige Fehlerinformationen über `IDispatch` und VTBL-Schnittstellen. Um anzugeben, dass ein Fehlerhandler verfügbar ist, sollten Sie die `ISupportErrorInfo` -Schnittstelle implementieren.

Um den Fehler Behandlungs Mechanismus zu veranschaulichen, gehen Sie davon aus, dass die von ClassWizard generierten Funktionen, die zum Implementieren der Standard dispatchunterstützung verwendet werden, Ausnahmen auslösen. Die MFC-Implementierung `IDispatch::Invoke` von fängt diese Ausnahmen in der Regel ab und konvertiert sie in eine exceptinfo-Struktur `Invoke` , die durch den-Befehl zurückgegeben wird. Wenn jedoch die VTBL-Schnittstelle verwendet wird, sind Sie dafür verantwortlich, die Ausnahmen selbst abzufangen. Als Beispiel für den Schutz der Dual-Interface-Methoden:

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

`CATCH_ALL_DUAL`übernimmt die Rückgabe des korrekten Fehlercodes, wenn eine Ausnahme auftritt. `CATCH_ALL_DUAL`Konvertiert eine MFC-Ausnahme mithilfe der `ICreateErrorInfo` -Schnittstelle in OLE-Automatisierungs Informationen zur Fehlerbehandlung. (Ein Beispiel `CATCH_ALL_DUAL` Makro befindet sich in der Datei mfcdual. H im [ACDual](../overview/visual-cpp-samples.md) -Beispiel. Die Funktion, die Sie zum Behandeln von `DualHandleException`Ausnahmen aufruft, befindet sich in der Datei mfcdual. Cpp.) `CATCH_ALL_DUAL` bestimmt basierend auf dem Typ der aufgetretenen Ausnahme den Fehlercode, der zurückgegeben werden soll:

- [COleDispatchException](../mfc/reference/coledispatchexception-class.md) : `HRESULT` wird in diesem Fall mithilfe des folgenden Codes erstellt:

    ```cpp
    hr = MAKE_HRESULT(SEVERITY_ERROR, FACILITY_ITF, (e->m_wCode + 0x200));
    ```

   Dadurch wird ein `HRESULT` spezifischer für die Schnittstelle erstellt, die die Ausnahme verursacht hat. Der Fehlercode wird um 0x200 versetzt, um Konflikte mit System definierten `HRESULT`s für OLE-Standardschnittstellen zu vermeiden.

- [Cmemoryexception](../mfc/reference/cmemoryexception-class.md) : in diesem Fall `E_OUTOFMEMORY` wird zurückgegeben.

- Alle anderen Ausnahmen: in diesem Fall `E_UNEXPECTED` wird zurückgegeben.

Um anzugeben, dass der OLE-Automatisierungs Fehlerhandler verwendet wird, sollten Sie auch `ISupportErrorInfo` die-Schnittstelle implementieren.

Fügen Sie zunächst Code zu ihrer Automation-Klassendefinition hinzu, um `ISupportErrorInfo`anzuzeigen, dass Sie unterstützt.

Fügen Sie dann der Schnittstellen Zuordnung Ihrer Automation-Klasse Code hinzu, um `ISupportErrorInfo` die Implementierungs Klasse mit dem MFC- `QueryInterface` Mechanismus zuzuordnen. Die `INTERFACE_PART` -Anweisung entspricht der für `ISupportErrorInfo`definierten-Klasse.

Implementieren Sie abschließend die-Klasse, die `ISupportErrorInfo`zur Unterstützung von definiert ist

(Das [ACDual](../overview/visual-cpp-samples.md) -Beispiel enthält drei Makros für diese drei Schritte `DECLARE_DUAL_ERRORINFO`,, `DUAL_ERRORINFO_PART`und `IMPLEMENT_DUAL_ERRORINFO`, die alle in mfcdual enthalten sind. H.)

Im folgenden Beispiel wird eine Klasse implementiert, die `ISupportErrorInfo`zur Unterstützung von definiert ist `CAutoClickDoc`der Name der Automatisierungs Klasse und `IID_IDualAClick` ist die **IID** für die Schnittstelle, die die Fehlerquelle ist, die über das OLE-Automatisierungs Fehler Objekt gemeldet wird:

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
