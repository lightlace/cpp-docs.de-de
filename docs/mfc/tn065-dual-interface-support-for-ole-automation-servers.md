---
title: "TN065: Unterst&#252;tzung f&#252;r duale Schnittstellen f&#252;r OLE-Automatisierungsserver | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ACDUAL-Beispiel [MFC]"
  - "Automatisierungsserver, Dualschnittstellenunterstützung"
  - "duale Schnittstellen, OLE-Automatisierung"
  - "TN065"
ms.assetid: b5c8ed09-2f7f-483c-80fc-2a47ad896063
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# TN065: Unterst&#252;tzung f&#252;r duale Schnittstellen f&#252;r OLE-Automatisierungsserver
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert.  Daher können einige Verfahren und Themen veraltet oder falsch sein.  Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis erläutert, wie Sie Unterstützung für duale Schnittstellen einer MFC\-basierten OLE\-Automatisierungsserver\-Anwendung hinzufügt.  [ACDual](../top/visual-cpp-samples.md) Das Beispiel veranschaulicht Unterstützung für duale Schnittstellen, und der in diesem Beispielcode Hinweis wird von ACDual übernommen.  Die Makros, die in diesem Hinweis, wie `DECLARE_DUAL_ERRORINFO`, `DUAL_ERRORINFO_PART` und `IMPLEMENT_DUAL_ERRORINFO` beschrieben sind, sind Teil des ACDUAL\-Beispiels und können in MFCDUAL.H. gefunden werden.  
  
## Duale Schnittstellen  
 Obwohl OLE\-Automatisierung Ihnen ermöglicht, `IDispatch` eine Schnittstelle, eine VTBL\-Schnittstelle oder eine duale Schnittstelle \(die zu implementieren beide umgibt\), empfiehlt Microsoft stark, dass Sie dualen Schnittstellen für alle verfügbar gemachten OLE\-Automatisierungsobjekte implementieren.  Duale Schnittstellen weisen erhebliche Vorteile gegenüber nur für oder nur für VTBL Schnittstellen `IDispatch`:  
  
-   Das Binden kann von VTBL\-Schnittstelle oder zur Laufzeit von `IDispatch` zur Kompilierzeit stattfinden.  
  
-   OLE\-Automatisierungs\-Controller, die die VTBL\-Schnittstelle verwenden können, profitieren möglicherweise über verbesserte Leistung.  
  
-   Vorhandene OLE\-Automatisierungs\-Controller, die die `IDispatch`\-Schnittstelle verwenden, fahren fort, um zu funktionieren.  
  
-   Die VTBL\-Schnittstelle ist einfacher, von C\+\+ aus aufzurufen.  
  
-   Duale Schnittstellen sind für die Kompatibilität mit Visual Basic\-Objektstützfunktionen erforderlich.  
  
## Hinzufügen der Unterstützung von dualen Schnittstellen zu einer CCmdTarget\-basierten Klasse  
 Eine duale Schnittstelle ist eigentlich nur eine benutzerdefinierte Schnittstelle, die von `IDispatch` abgeleitet wird.  Die einfachste Methode, für duale Schnittstellen einer \- Klasse `CCmdTarget` implementieren Unterstützung steht zunächst implementieren die normale Dispatchschnittstelle auf der Klasse mit MFC und die, hinzufügen die benutzerdefinierte Schnittstelle höher.  In den meisten Fällen delegiert die benutzerdefinierte Schnittstellenimplementierung einfach zurück zur Implementierung MFC\-Klassen `IDispatch`.  
  
 Zuerst ändern Sie die ODL\-Datei für den Server, um duale Schnittstellen für die Objekte definieren.  Um eine duale Schnittstelle zu definieren, müssen Sie eine Schnittstellenanweisung, anstelle der `DISPINTERFACE`\-Anweisung verwenden die die Visual C\+\+\-Assistenten generieren.  Anstatt, die vorhandene `DISPINTERFACE`\-Anweisung entfernt werden, fügen Sie eine neue Schnittstellenanweisung hinzu.  Mit dem `DISPINTERFACE` Formular beibehalten, können Sie weiterhin, um die zu verwenden, um Eigenschaften und Methoden das Objekt hinzuzufügen, aber Sie müssen die erforderlichen Eigenschaften und Methoden der Schnittstellenanweisung hinzufügen.  
  
 Eine Schnittstellenanweisung für eine duale Schnittstelle muss die **OLEAUTOMATION** und **DUAL** über Attribute verfügen, und die Schnittstelle muss von `IDispatch` abgeleitet werden.  Sie können das [GUIDGEN](../top/visual-cpp-samples.md) beispielsweise verwenden, um die **IID** für duale Schnittstelle zu erstellen:  
  
```  
[ uuid(0BDD0E81-0DD7-11cf-BBA8-444553540000), // IID_IDualAClick  
   oleautomation,  
   dual  
]  
interface IDualAClick : IDispatch  
  {  
  };  
```  
  
 Sobald Sie die Schnittstellenanweisung bereit haben, starten Sie das Hinzufügen von Einträgen für die Methoden und Eigenschaften.  Eine duale Schnittstellen müssen die Parameterlisten neu anordnen, damit Ihre Methoden und Eigenschaftenaccessorfunktionen in der dualen Schnittstellenoption `HRESULT` zurückgeben und die Rückgabewerte als Parameter mit den Attributen `[retval,out]` übergeben.  Beachten Sie, dass für Eigenschaften, Sie einen `propget` hinzufügen \(Lesen\) und \(`propput`\) mit Zugriffsfunktion derselben ID schreiben müssen  Beispiel:  
  
```  
[propput, id(1)] HRESULT text([in] BSTR newText);  
[propget, id(1)] HRESULT text([out, retval] BSTR* retval);  
```  
  
 Nach den Methoden und Eigenschaften werden, müssen Sie einen Verweis auf die Schnittstellenanweisung in der Co\-Klassenanweisung hinzufügen definiert.  Beispiel:  
  
```  
[ uuid(4B115281-32F0-11cf-AC85-444553540000) ]  
coclass Document  
{  
   dispinterface IAClick;  
   [default] interface IDualAClick;  
};  
```  
  
 Sobald die ODL\-Datei aktualisiert wurde, verwenden Sie Schnittstellen\-Zuordnungsmechanismus MFC, um die Implementierungsklasse eine für duale Schnittstelle in der Klasse definieren und die entsprechenden Einträgen in `QueryInterface` Mechanismus MFC\-Programm zu machen.  Sie benötigen einen Eintrag im `INTERFACE_PART`\-Block für jeden Eintrag in der Schnittstellenanweisung des ODL, plus die Einträge für eine Dispatchschnittstelle.  Jeder ODL\-Eintrag mit dem **propput**\-Attribut erfordert eine Funktion, die `put_propertyname` genannt wird.  Jeder Eintrag mit dem **propget**\-Attribut erfordert eine Funktion, die `get_propertyname` genannt wird.  
  
 Um eine der Implementierungsklasse duale Schnittstelle zu definieren, fügen Sie einem `DUAL_INTERFACE_PART` der Block Objektklassendefinition hinzu.  Beispiel:  
  
```  
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
  
 Um die duale Schnittstelle an [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms687230) Mechanismus MFC herzustellen, fügen Sie einem `INTERFACE_PART` der Schnittstellenzuordnung Eintrag hinzu:  
  
```  
BEGIN_INTERFACE_MAP(CAutoClickDoc, CDocument)  
  INTERFACE_PART(CAutoClickDoc, DIID_IAClick, Dispatch)  
  INTERFACE_PART(CAutoClickDoc, IID_IDualAClick, DualAClick)  
END_INTERFACE_MAP()  
```  
  
 Danach müssen Sie die Implementierung der Schnittstelle füllen.  In den meisten Fällen bieten die Möglichkeit, die vorhandene Implementierung MFC\-Klassen `IDispatch` zu delegieren.  Beispiel:  
  
```  
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
             REFIID iid, LPVOID* ppvObj)  
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
          UINT itinfo, LCID lcid, ITypeInfo FAR* FAR* pptinfo)  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);  
   ASSERT(lpDispatch != NULL);  
   return lpDispatch->GetTypeInfo(itinfo, lcid, pptinfo);  
}  
STDMETHODIMP CAutoClickDoc::XDualAClick::GetIDsOfNames(  
       REFIID riid, OLECHAR FAR* FAR* rgszNames, UINT cNames,  
       LCID lcid, DISPID FAR* rgdispid)   
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);  
   ASSERT(lpDispatch != NULL);  
   return lpDispatch->GetIDsOfNames(riid, rgszNames, cNames,   
                                    lcid, rgdispid);  
}  
STDMETHODIMP CAutoClickDoc::XDualAClick::Invoke(  
    DISPID dispidMember, REFIID riid, LCID lcid, WORD wFlags,  
    DISPPARAMS FAR* pdispparams, VARIANT FAR* pvarResult,  
    EXCEPINFO FAR* pexcepinfo, UINT FAR* puArgErr)  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);  
   ASSERT(lpDispatch != NULL);  
   return lpDispatch->Invoke(dispidMember, riid, lcid,  
                             wFlags, pdispparams, pvarResult,  
                             pexcepinfo, puArgErr);  
}  
```  
  
 Für die Methoden des Objekts und die Eigenschaftenaccessorfunktionen müssen Sie die Implementierung gefüllt.  die Methode und Eigenschaftenfunktionen können wieder die Methoden im Allgemeinen einen Delegat, die mithilfe die generiert werden.  Wenn Sie jedoch Eigenschaften installieren, die in Variablen direkt zugreifen, müssen Sie, den Code schreiben, um abzurufen bzw. legen den Wert in die Variable.  Beispiel:  
  
```  
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
  
## Übergeben von Zeigern auf duale Schnittstellen  
 den Mauszeiger zu übergeben für duale Schnittstellen ist nicht leicht, insbesondere wenn Sie `CCmdTarget::FromIDispatch` aufrufen müssen.  Arbeiten `FromIDispatch` nur über `IDispatch` Zeiger MFC.  Eine Möglichkeit, das verwendet werden kann, für das ursprüngliche `IDispatch` Zeigersetup durch MFC abfragen und diesen Zeiger an Funktionen übergeben, die sie benötigen.  Beispiel:  
  
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
  
 Bevor Sie eine Zeigerrückseite von der Methode für duale Schnittstellen haben, müssen Sie möglicherweise die im Zeiger MFC `IDispatch` dem Zeiger konvertieren für duale Schnittstellen.  Beispiel:  
  
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
  
## Registrieren der Typbibliothek der Anwendung  
 Anwendungs\-Assistent generiert kein Code, um eine Typbibliothek der OLE\-Automatisierungsserver\-Anwendung mit dem System zu registrieren.  Während es andere Möglichkeiten gibt, die Typbibliothek zu registrieren, ist es hilfreich, das Anwendungsregister verfügen die Typbibliothek, wenn es die OLE\-Typinformationen d. h aktualisiert wenn die Anwendung ausgeführt eigenständiges ist.  
  
 So die Typbibliothek der Anwendung registrieren, wenn die Anwendung eigentlich ausgeführt wird:  
  
-   Zu AFXCTL.H im Standard schließung Headerdatei, STDAFX.H Ein, um die Definition der `AfxOleRegisterTypeLib`\-Funktion zu.  
  
-   In `InitInstance`\-Funktion der Anwendung lokalisieren Sie den Aufruf von `COleObjectFactory::UpdateRegistryAll`.  Nach diesem Aufruf Fügen Sie `AfxOleRegisterTypeLib` einen Aufruf hinzu und **LIBID** anhand Ihrer Typbibliothek, zusammen mit dem Namen der Typbibliothek angeben:  
  
    ```  
    // When a server application is launched stand-alone, it is a good idea  
    // to update the system registry in case it has been damaged.  
    m_server.UpdateRegistry(OAT_DISPATCH_OBJECT);  
    COleObjectFactory::UpdateRegistryAll();  
    // DUAL_SUPPORT_START  
    // Make sure the type library is registered or dual interface won't work.  
    AfxOleRegisterTypeLib(AfxGetInstanceHandle(), LIBID_ACDual, _T("AutoClik.TLB"));  
    // DUAL_SUPPORT_END  
    ```  
  
## Ändern von Projekt\-Build\-Einstellungen, um Typbibliotheks\-Änderungen anzupassen  
 So passen Sie die Buildeinstellungen eines Projekts ändern, sodass eine Headerdatei, die die Definitionen enthält **UUID**, durch MkTypLib generiert wird, wenn die Typbibliothek neu erstellt wird:  
  
1.  Klicken Sie im Menü **Erstellen** klicken Sie auf **Einstellungen** und wählen Sie dann die ODL\-Datei der Dateiliste für jede Konfiguration aus.  
  
2.  Klicken Sie auf die Registerkarte **OLE\-Typen** und geben Sie einen Dateinamen auf das **Ausgabeheader** \- Feld an.  Verwenden Sie einen Dateinamen, der noch nicht vom Projekt verwendet wird, da MkTypLib eine vorhandene Datei überschrieben.  Klicken auf **OKBuildeinstellungen**, um das Dialogfeld zu schließen.  
  
 So den **UUID** Definitionen von der MkTypLib\-generierten Headerdatei dem Projekt hinzufügen:  
  
1.  Schließung Sie die MkTypLib\-generierte Headerdatei in die Standardeinschließungsheaderdatei, STDAFX.H. Ein.  
  
2.  Erstellen Sie eine neue Datei, INITIIDS.CPP, und fügen Sie sie dem Projekt hinzu.  In dieser Datei fügen Sie die MkTypLib\-generierte Headerdatei anschließend einschließlich OLE2.H und INITGUID.H ein:  
  
    ```  
    // initIIDs.c: defines IIDs for dual interfaces  
    // This must not be built with precompiled header.  
      #include <ole2.h>  
      #include <initguid.h>  
      #include "acdual.h"  
    ```  
  
3.  Klicken Sie im Menü **Erstellen** klicken Sie auf **Einstellungen** und wählen Sie dann INITIIDS.CPP der Dateiliste für jede Konfiguration aus.  
  
4.  Klicken Sie auf die Registerkarte **C\+\+**, klicken Sie auf Kategorie **Vorkompilierte Header** und wählen Sie das Optionsfeld **Vorkompilierte Header werden nicht verwendet** aus.  Klicken Sie auf OK, um das **Buildeinstellungen** Dialogfeld zu schließen.  
  
## Angeben des richtigen Objektklassen\-Namens in der Typbibliothek  
 Die Assistenten, die mit Visual C\+\+ zurückgreifen mitgelieferten falsch, den Implementierungsklassennamen, um die Co\-Klasse in das der ODL\-Datei des Servers für OLE\-erstellbare Klassen anzugeben.  Während das funktioniert, ist der Implementierungsklassenname wahrscheinlich nicht der Klassenname, den Sie Benutzer des Objekts zur Verwendung soll.  So dem richtigen Namen angeben, die ODL\-Datei öffnen, jede Co\-Klassenanweisung suchen, und den Implementierungsklassennamen vom richtigen externen Namen ersetzen.  
  
 Beachten Sie, dass, wenn der Co\-Klassenanweisung geändert wird, die Variablennamen von **CLSID**s in der MkTypLib\-generierten Headerdatei entsprechend ändern.  Sie müssen den Code aktualisieren, um die Variablennamen neuen zu verwenden.  
  
## Behandeln von Ausnahmen und die Automatisierungs\-Fehler\-Schnittstellen  
 Die Methoden des Automatisierungsobjekts und die Eigenschaftenaccessorfunktionen lösen möglicherweise Ausnahmen aus.  In diesem Fall sollten Sie sie in Ihrer Implementierung behandeln für duale Schnittstellen und Informationen über die Ausnahme an den Controller von der OLE\-Automatisierungs\-Fehlerbehandlungsschnittstelle übergeben, **IErrorInfo**.  Diese Schnittstelle enthält die ausführlichen, kontextbedingten Fehlerinformationen von `IDispatch` und VTBL\-Schnittstellen bereit.  Um anzugeben dass ein Fehlerhandler verfügbar ist, sollten Sie die **ISupportErrorInfo**\-Schnittstelle implementieren.  
  
 Um dem Fehlerbehandlungsmechanismus zu veranschaulichen, nehmen Sie die ClassWizard\-generierten Funktionen, die verwendet werden um die Standarddispatchstützwurfsausnahmen zu implementieren.  Implementierung MFC von **IDispatch::Invoke** normalerweise fängt diese Ausnahme ab und konvertiert sie in eine EXCEPTINFO\-Struktur, die durch den Aufruf `Invoke` zurückgegeben wird.  Wenn VTBL\-Schnittstelle verwendet wird, sind Sie für das Abfangen der Ausnahmen selbst verantwortlich.  Als Beispiel zum Schützen der Methoden für duale Schnittstellen:  
  
```  
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
  
 `CATCH_ALL_DUAL` verarbeitet die um Zurückgeben des richtigen Fehlercodes, wenn eine Ausnahme auftritt.  `CATCH_ALL_DUAL` konvertiert eine MFC\-Ausnahme in OLE\-Automatisierungs\-Fehlerbehandlungsinformationen mithilfe der **ICreateErrorInfo**\-Schnittstelle. \(Ein Beispiel `CATCH_ALL_DUAL`\-Makro ist in der Datei MFCDUAL.H im Beispiel [ACDual](../top/visual-cpp-samples.md).  Die Funktion, die aufgerufen wird, um Ausnahmen zu behandeln, `DualHandleException`, ist in der Datei MFCDUAL.CPP.\) `CATCH_ALL_DUAL` bestimmt den Fehlercode, um auf Grundlage des Typs der Ausnahme zurück, der aufgetreten ist:  
  
-   [COleDispatchException](../mfc/reference/coledispatchexception-class.md) \- in diesem Fall wird `HRESULT` mithilfe des folgenden Codes erstellt:  
  
    ```  
    hr = MAKE_HRESULT(SEVERITY_ERROR, FACILITY_ITF,   
                               (e->m_wCode + 0x200));  
    ```  
  
     Dies erstellt ein `HRESULT` Besonderheiten der Schnittstelle, die die Ausnahme verursacht hat.  Der Fehlercode wird durch 0x200 ausbalanciert, um alle Konflikte mit systemdefiniertem `HRESULT` für Standard\-OLE\-Schnittstellen zu vermeiden.  
  
-   [CMemoryException](../mfc/reference/cmemoryexception-class.md) \- in diesem Fall wird `E_OUTOFMEMORY` zurückgegeben.  
  
-   Eine andere Ausnahme \- in diesem Fall wird `E_UNEXPECTED` zurückgegeben.  
  
 Um anzugeben dass der OLE\-Automatisierungs\-Fehlerhandler verwendet wird, sollten Sie die **ISupportErrorInfo** auch Schnittstelle implementieren.  
  
 Zuerst fügen Sie Code der Automatisierungsklassendefinition hinzu, um diese anzuzeigen, dass **ISupportErrorInfo** unterstützt.  
  
 Zweitens fügen Sie Code der Schnittstellenzuordnung Automatisierungsklasse hinzu, um die Implementierungsklasse **ISupportErrorInfo** mit `QueryInterface` Mechanismus MFC zuzuordnen.  Die Anweisung `INTERFACE_PART` entspricht die Klasse ab, die für **ISupportErrorInfo** definiert wird.  
  
 Schließlich implementieren Sie die Klasse, die definiert wird, um die **ISupportErrorInfo** zu unterstützen.  
  
 \(Das [ACDual](../top/visual-cpp-samples.md) Beispiel enthält drei Makros, um zu helfen tun diese drei Schritte, `DECLARE_DUAL_ERRORINFO`, `DUAL_ERRORINFO_PART` und `IMPLEMENT_DUAL_ERRORINFO`, ähnlich enthalten in MFCDUAL.H.\)  
  
 Das nächste Beispiel implementiert eine Klasse, die definiert wird, um die **ISupportErrorInfo** zu unterstützen.  `CAutoClickDoc` ist der Name der Automatisierungsklasse und `IID_IDualAClick` ist **IID** für die Schnittstelle, die die Fehlerquelle gemeldet durch das OLE\-Automatisierungs\-Fehlerobjekt ist:  
  
```  
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
   REFIID iid, LPVOID* ppvObj)   
{   
   METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)   
   return pThis->ExternalQueryInterface(&iid, ppvObj);   
}   
STDMETHODIMP CAutoClickDoc::XSupportErrorInfo::InterfaceSupportsErrorInfo(   
   REFIID iid)   
{   
   METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)   
   return (iid == IID_IDualAClick) ? S_OK : S_FALSE;   
}  
```  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)