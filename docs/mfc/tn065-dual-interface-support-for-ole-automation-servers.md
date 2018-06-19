---
title: 'TN065: Unterstützung für duale Schnittstellen für OLE-Automatisierungsserver | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 3b1c0d30938529d9eb432e6171b546a42f87905a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33386068"
---
# <a name="tn065-dual-interface-support-for-ole-automation-servers"></a>TN065: Unterstützung für duale Schnittstellen für OLE-Automatisierungsserver
> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis erläutert, wie eine Anwendung mit OLE-Automatisierungsserver MFC-basierte Unterstützung für duale Schnittstellen hinzu. Die [ACDUAL](../visual-cpp-samples.md) Beispiel veranschaulicht wird die Unterstützung für duale Schnittstellen und der Beispielcode in diesem Hinweis ACDUAL entnommen. Die Makros wie in diesem Hinweis beschriebenen `DECLARE_DUAL_ERRORINFO`, `DUAL_ERRORINFO_PART`, und `IMPLEMENT_DUAL_ERRORINFO`, sind Teil der ACDUAL-Beispiel und in MFCDUAL gefunden werden können. H.  
  
## <a name="dual-interfaces"></a>Duale Schnittstellen  
 OLE-Automatisierung können Sie implementieren eine `IDispatch` -Schnittstelle, eine VTBL-Schnittstelle oder eine duale Schnittstelle (umfasst sowohl), empfiehlt Microsoft dringend, dass Sie für alle OLE-Automatisierungsobjekte verfügbar gemachte duale Schnittstellen implementieren. Duale Schnittstellen haben erhebliche Vorteile gegenüber `IDispatch`- oder nur VTBL-Schnittstellen:  
  
-   Bindung kann zur Kompilierzeit über die VTBL-Schnittstelle, oder stattfinden zur Laufzeit über `IDispatch`.  
  
-   OLE-Automatisierungscontroller, die den VTBL-Schnittstelle verwenden, können möglicherweise von einer verbesserten Leistung profitieren.  
  
-   Vorhandenen OLE-Automatisierungscontroller, mit denen die `IDispatch` Schnittstelle sind weiterhin funktionsfähig.  
  
-   Die VTBL-Schnittstelle ist einfacher, die von C++ aus aufzurufen.  
  
-   Duale Schnittstellen sind erforderlich, um die Kompatibilität mit Funktionen zur Unterstützung von Visual Basic-Objekt.  
  
## <a name="adding-dual-interface-support-to-a-ccmdtarget-based-class"></a>Hinzufügen von Unterstützung für duale zu einer basierende CCmdTarget-Klasse  
 Eine duale Schnittstelle ist genau genommen nur eine benutzerdefinierte Schnittstelle abgeleitet `IDispatch`. Die einfachste Möglichkeit zum Implementieren der Unterstützung für duale Schnittstellen in einem `CCmdTarget`-Basis-Klasse wird zum ersten implementieren die normale Verteilung-Schnittstelle für die Klasse, die mithilfe von MFC und ClassWizard, und klicken Sie dann die benutzerdefinierte Schnittstelle später hinzufügen. Ihre benutzerdefinierte Implementierung wird größtenteils, einfach delegieren, zurück an die MFC-Bibliothek `IDispatch` Implementierung.  
  
 Ändern Sie zunächst ODL-Datei für Ihren Server duale Schnittstellen für die Objekte zu definieren. Um eine duale Schnittstelle zu definieren, müssen Sie eine Interface-Anweisung verwenden, statt die `DISPINTERFACE` -Anweisung, die Visual C++-Assistenten generieren. Anstatt zu entfernen, die vorhandene `DISPINTERFACE` -Anweisung, fügen Sie eine neue Schnittstelle-Anweisung hinzu. Durch Beibehalten der `DISPINTERFACE` Formular können Sie weiterhin ClassWizard zu verwenden, um Eigenschaften und Methoden für Ihr Objekt hinzuzufügen, aber Sie müssen die entsprechenden Eigenschaften und Methoden Interface-Anweisung hinzufügen.  
  
 Eine Schnittstelle-Anweisung für eine duale Schnittstelle benötigen die **OLEAUTOMATION** und **DUALE** Attribute und die Schnittstelle muss von abgeleitet werden `IDispatch`. Können Sie die [GUIDGEN](../visual-cpp-samples.md) -Beispiel zum Erstellen einer **IID** für die duale Schnittstelle:  
  
```  
[ uuid(0BDD0E81-0DD7-11cf-BBA8-444553540000), // IID_IDualAClick  
    oleautomation, 
    dual 
]  
interface IDualAClick : IDispatch  
 {  
 };  
```  
  
 Sobald Sie die Interface-Anweisung vorbereitet haben, starten Sie die Einträge für die Methoden und Eigenschaften hinzufügt. Für duale Schnittstellen müssen Sie die Parameterlisten neu anordnen, dass die Methoden und die Eigenschaft Accessor-Funktionen in der dualen Schnittstelle zurückgeben einer `HRESULT` und die Rückgabewerte übergeben, als Parameter mit den Attributen `[retval,out]`. Denken Sie daran, dass für Eigenschaften, Sie benötigen beide einen Lesevorgang hinzufügen (`propget`) und Schreiben (`propput`) Zugriff auf die Funktion mit der gleichen Id. Zum Beispiel:  
  
```  
[propput,
    id(1)] HRESULT text([in] BSTR newText);

[propget,
    id(1)] HRESULT text([out,
    retval] BSTR* retval);
```  
  
 Nachdem Ihre Methoden und Eigenschaften definiert wurden, müssen Sie einen Verweis auf die Interface-Anweisung in der Co-Klasse-Anweisung hinzufügen. Zum Beispiel:  
  
```  
[ uuid(4B115281-32F0-11cf-AC85-444553540000) ]  
coclass Document  
{  
    dispinterface IAClick;  
 [default] interface IDualAClick;  
};  
```  
  
 Sobald die ODL-Datei aktualisiert wurde, mit der schnittstellenzuordnungsmechanismus von MFC definieren eine Implementierungsklasse für die duale Schnittstelle in der Objektklasse, und stellen die entsprechenden Einträge in MFC `QueryInterface` Mechanismus. Sie benötigen einen Eintrag in der `INTERFACE_PART` Block für jeden Eintrag in der Schnittstelle-Anweisung die ODL plus die Einträge für eine Dispatch-Schnittstelle. Jeder ODL-Eintrag mit dem **Propput** Attribut benötigt eine Funktion namens `put_propertyname`. Jeder Eintrag mit dem **Propget** Attribut benötigt eine Funktion namens `get_propertyname`.  
  
 Um eine Implementierungsklasse für die duale Schnittstelle zu definieren, fügen einen `DUAL_INTERFACE_PART` Block auf Ihre Objektklassendefinition. Zum Beispiel:  
  
```  
BEGIN_DUAL_INTERFACE_PART(DualAClick,
    IDualAClick)  
    STDMETHOD(put_text)(THIS_ BSTR newText);

    STDMETHOD(get_text)(THIS_ BSTR FAR* retval);

    STDMETHOD(put_x)(THIS_ short newX);

    STDMETHOD(get_x)(THIS_ short FAR* retval);

    STDMETHOD(put_y)(THIS_ short newY);

    STDMETHOD(get_y)(THIS_ short FAR* retval);

    STDMETHOD(put_Position)(THIS_ IDualAutoClickPoint FAR* newPosition);

    STDMETHOD(get_Position)(THIS_ IDualAutoClickPoint FAR* FAR* retval);

    STDMETHOD(RefreshWindow)(THIS);

 STDMETHOD(SetAllProps)(THIS_ short x,
    short y,
    BSTR text);

    STDMETHOD(ShowWindow)(THIS);

END_DUAL_INTERFACE_PART(DualAClick) 
```  
  
 Zur Verbindung mit der MFC-dualen Schnittstelle [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms687230) Mechanismus, Hinzufügen einer `INTERFACE_PART` Eintrag, um die schnittstellenzuordnung:  
  
```  
BEGIN_INTERFACE_MAP(CAutoClickDoc,
    CDocument)  
    INTERFACE_PART(CAutoClickDoc,
    DIID_IAClick,
    Dispatch)  
    INTERFACE_PART(CAutoClickDoc,
    IID_IDualAClick,
    DualAClick)  
END_INTERFACE_MAP()  
```  
  
 Als Nächstes müssen Sie in der Implementierung der Schnittstelle zu füllen. Meistens, Sie werden für die Delegierung an die MFC-Bibliothek vorhandene `IDispatch` Implementierung. Zum Beispiel:  
  
```  
STDMETHODIMP_(ULONG) CAutoClickDoc::XDualAClick::AddRef()  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    return pThis->ExternalAddRef();

}  
STDMETHODIMP_(ULONG) CAutoClickDoc::XDualAClick::Release()  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    return pThis->ExternalRelease();

}  
STDMETHODIMP CAutoClickDoc::XDualAClick::QueryInterface(
    REFIID iid,
    LPVOID* ppvObj)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    return pThis->ExternalQueryInterface(&iid,
    ppvObj);

}  
STDMETHODIMP CAutoClickDoc::XDualAClick::GetTypeInfoCount(
    UINT FAR* pctinfo)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);

    ASSERT(lpDispatch != NULL);

    return lpDispatch->GetTypeInfoCount(pctinfo);

}  
STDMETHODIMP CAutoClickDoc::XDualAClick::GetTypeInfo(
    UINT itinfo,
    LCID lcid,
    ITypeInfo FAR* FAR* pptinfo)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);

    ASSERT(lpDispatch != NULL);

    return lpDispatch->GetTypeInfo(itinfo,
    lcid,
    pptinfo);

}  
STDMETHODIMP CAutoClickDoc::XDualAClick::GetIDsOfNames(
    REFIID riid,
    OLECHAR FAR* FAR* rgszNames,
    UINT cNames,  
    LCID lcid,
    DISPID FAR* rgdispid)   
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);

    ASSERT(lpDispatch != NULL);

    return lpDispatch->GetIDsOfNames(riid,
    rgszNames,
    cNames,   
    lcid,
    rgdispid);

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
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);

    ASSERT(lpDispatch != NULL);

    return lpDispatch->Invoke(dispidMember,
    riid,
    lcid,  
    wFlags,
    pdispparams,
    pvarResult,  
    pexcepinfo,
    puArgErr);

}  
```  
  
 Für Methoden und Accessorfunktionen der Eigenschaft des Objekts müssen Sie in der Implementierung zu füllen. Methoden- und Funktionen können in der Regel an die Methoden, die mithilfe der Klassen-Assistent generiert delegieren. Wenn Sie Eigenschaften direkt den Zugriff auf Variablen einrichten, müssen Sie jedoch den Code, um Get/Put von den Wert in die Variable zu schreiben. Zum Beispiel:  
  
```  
STDMETHODIMP CAutoClickDoc::XDualAClick::put_text(BSTR newText)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick) *// MFC automatically converts from Unicode BSTR to *// Ansi CString,
    if necessary...  
    pThis->m_str = newText;  
    return NOERROR;  
}  
STDMETHODIMP CAutoClickDoc::XDualAClick::get_text(BSTR* retval)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick) *// MFC automatically converts from Ansi CString to *// Unicode BSTR,
    if necessary...  
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
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
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
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDisp;  
    lpDisp = pThis->GetPosition();
lpDisp->QueryInterface(IID_IDualAutoClickPoint, (LPVOID*)retval);

    return NOERROR;  
}  
```  
  
## <a name="registering-the-applications-type-library"></a>Beim Registrieren der Typbibliothek für die Anwendung  
 AppWizard generiert keinen Code aus, um die Typbibliothek für ein OLE-Automatisierung Server-Anwendung mit dem System zu registrieren. Dafür gibt es weitere Möglichkeiten zum Registrieren der Typbibliothek, empfiehlt es sich, dass die Anwendung die Typbibliothek zu registrieren, wenn die OLE-Typinformationen, also aktualisiert wird, wenn die Anwendung eigenständigen ausgeführt wird.  
  
 Zum Registrieren der Anwendung Typbibliothek, wenn die Anwendung ausgeführt wird eigenständig:  
  
-   AFXCTL einschließen H in Ihrem Standard umfasst Headerdatei STDAFX. H, die Definition der Zugriff auf die `AfxOleRegisterTypeLib` Funktion.  
  
-   In der Anwendungsverzeichnis `InitInstance` funktionieren, suchen Sie den Aufruf von `COleObjectFactory::UpdateRegistryAll`. Fügen Sie nach diesem Aufruf einen Aufruf von `AfxOleRegisterTypeLib`unter Angabe der **LIBID** , die Typbibliothek, zusammen mit dem Namen der Typbibliothek entspricht:  
  
 "" * / / Wenn eine Serveranwendung eigenständigen gestartet wird, ist es eine gute Idee * / / die systemregistrierung aktualisiert wird, für den Fall, dass er beschädigt wurde.  
    m_server.UpdateRegistry(OAT_DISPATCH_OBJECT);

 COleObjectFactory::UpdateRegistryAll(); * / / DUAL_SUPPORT_START * / / stellen Sie sicher, dass die Typbibliothek registriert ist oder duale Schnittstelle funktioniert nicht.  
AfxOleRegisterTypeLib(AfxGetInstanceHandle() LIBID_ACDual, _T("AutoClik.TLB")); * / / DUAL_SUPPORT_END  
 ```  
  
## Modifying Project Build Settings to Accommodate Type Library Changes  
 To modify a project's build settings so that a header file containing **UUID** definitions is generated by MkTypLib whenever the type library is rebuilt:  
  
1.  On the **Build** menu, click **Settings**, and then select the ODL file from the file list for each configuration.  
  
2.  Click the **OLE Types** tab and specify a filename in the **Output header** filename field. Use a filename that is not already used by your project, because MkTypLib will overwrite any existing file. Click **OK** to close the **Build Settings** dialog box.  
  
 To add the **UUID** definitions from the MkTypLib-generated header file to your project:  
  
1.  Include the MkTypLib-generated header file in your standard includes header file, STDAFX.H.  
  
2.  Create a new file, INITIIDS.CPP, and add it to your project. In this file, include your MkTypLib-generated header file after including OLE2.H and INITGUID.H:  
  
 ```  
    initIIDs.c: definiert von IIDs für duale Schnittstellen  
    Dadurch muss nicht mit vorkompilierten Header erstellt werden.  
      #<a name="include-ole2h"></a>Einschließen von < ole2.h >  
      #<a name="include-initguidh"></a>Schließen Sie < initguid.h >  
      #<a name="include-acdualh"></a>"acdual.h" enthalten  
 ```  
  
3.  On the **Build** menu, click **Settings**, and then select INITIIDS.CPP from the file list for each configuration.  
  
4.  Click the **C++** tab, click category **Precompiled Headers**, and select the **Not using precompiled headers** radio button. Click OK to close the **Build Settings** dialog box.  
  
## Specifying the Correct Object Class Name in the Type Library  
 The wizards shipped with Visual C++ incorrectly use the implementation class name to specify the coclass in the server's ODL file for OLE-creatable classes. While this will work, the implementation class name is probably not the class name you want users of your object to use. To specify the correct name, open the ODL file, locate each coclass statement, and replace the implementation class name with the correct external name.  
  
 Note that when the coclass statement is changed, the variable names of **CLSID**s in the MkTypLib-generated header file will change accordingly. You will need to update your code to use the new variable names.  
  
## Handling Exceptions and the Automation Error Interfaces  
 Your automation object's methods and property accessor functions may throw exceptions. If so, you should handle them in your dual-interface implementation and pass information about the exception back to the controller through the OLE Automation error-handling interface, **IErrorInfo**. This interface provides for detailed, contextual error information through both `IDispatch` and VTBL interfaces. To indicate that an error handler is available, you should implement the **ISupportErrorInfo** interface.  
  
 To illustrate the error-handling mechanism, assume that the ClassWizard-generated functions used to implement the standard dispatch support throw exceptions. MFC's implementation of **IDispatch::Invoke** typically catches these exceptions and converts them into an EXCEPTINFO structure that is returned through the `Invoke` call. However, when VTBL interface is used, you are responsible for catching the exceptions yourself. As an example of protecting your dual-interface methods:  
  
```  
STDMETHODIMP CAutoClickDoc::XDualAClick::put_text(BSTR newText)  
{  
    METHOD_PROLOGUE (CAutoClickDoc, DualAClick)  
    TRY_DUAL(IID_IDualAClick) {* / / MFC automatisch konvertiert, aus Unicode BSTR * / / Ansi CString, bei Bedarf...  
    pThis->m_str = newText;  
    Geben Sie NOERROR zurück.  
 }  
    CATCH_ALL_DUAL}  
```  
  
 `CATCH_ALL_DUAL` takes care of returning the correct error code when an exception occurs. `CATCH_ALL_DUAL` converts an MFC exception into OLE Automation error-handling information using the **ICreateErrorInfo** interface. (An example `CATCH_ALL_DUAL` macro is in the file MFCDUAL.H in the [ACDUAL](../visual-cpp-samples.md) sample. The function it calls to handle exceptions, `DualHandleException`, is in the file MFCDUAL.CPP.) `CATCH_ALL_DUAL` determines the error code to return based on the type of exception that occurred:  
  
- [COleDispatchException](../mfc/reference/coledispatchexception-class.md) - In this case, `HRESULT` is constructed using the following code:  
  
 ```  
    hr = MAKE_HRESULT(SEVERITY_ERROR,
    FACILITY_ITF,   
 (e -> M_wCode + 0 x 200));

 ```  
  
     This creates an `HRESULT` specific to the interface that caused the exception. The error code is offset by 0x200 to avoid any conflicts with system-defined `HRESULT`s for standard OLE interfaces.  
  
- [CMemoryException](../mfc/reference/cmemoryexception-class.md) - In this case, `E_OUTOFMEMORY` is returned.  
  
-   Any other exception - In this case, `E_UNEXPECTED` is returned.  
  
 To indicate that the OLE Automation error handler is used, you should also implement the **ISupportErrorInfo** interface.  
  
 First, add code to your automation class definition to show it supports **ISupportErrorInfo**.  
  
 Second, add code to your automation class's interface map to associate the **ISupportErrorInfo** implementation class with MFC's `QueryInterface` mechanism. The `INTERFACE_PART` statement matches the class defined for **ISupportErrorInfo**.  
  
 Finally, implement the class defined to support **ISupportErrorInfo**.  
  
 (The [ACDUAL](../visual-cpp-samples.md) sample contains three macros to help do these three steps, `DECLARE_DUAL_ERRORINFO`, `DUAL_ERRORINFO_PART`, and `IMPLEMENT_DUAL_ERRORINFO`, all contained in MFCDUAL.H.)  
  
 The following example implements a class defined to support **ISupportErrorInfo**. `CAutoClickDoc` is the name of your automation class and `IID_IDualAClick` is the **IID** for the interface that is the source of errors reported through the OLE Automation error object:  
  
```  
STDMETHODIMP_(ulong) CAutoClickDoc::XSupportErrorInfo::AddRef()   
{  
    METHOD_PROLOGUE (CAutoClickDoc, SupportErrorInfo)   
    return pThis-ExternalAddRef() >;

}   
STDMETHODIMP_(ulong) CAutoClickDoc::XSupportErrorInfo::Release()   
{   
    METHOD_PROLOGUE (CAutoClickDoc, SupportErrorInfo)   
    return pThis-ExternalRelease() >;

}   
STDMETHODIMP CAutoClickDoc::XSupportErrorInfo::QueryInterface (REFIID Iid, LPVOID * PpvObj)   
{   
    METHOD_PROLOGUE (CAutoClickDoc, SupportErrorInfo)   
    ExternalQueryInterface (& Iid, PpvObj); return pThis ->

}   
STDMETHODIMP CAutoClickDoc::XSupportErrorInfo::InterfaceSupportsErrorInfo (REFIID Iid)   
{   
    METHOD_PROLOGUE (CAutoClickDoc, SupportErrorInfo)   
    zurückgeben (Iid == IID_IDualAClick) S_OK: "S_FALSE";   
}  
```  
  
## See Also  
 [Technical Notes by Number](../mfc/technical-notes-by-number.md)   
 [Technical Notes by Category](../mfc/technical-notes-by-category.md)

