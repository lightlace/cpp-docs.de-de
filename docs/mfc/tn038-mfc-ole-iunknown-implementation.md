---
title: 'Tn038: Implementieren von MFC-OLE-IUnknown-Implementierung | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.ole
dev_langs:
- C++
helpviewer_keywords:
- aggregation macros [MFC]
- COM interfaces, base interface
- IUnknown interface
- END_INTERFACE_MAP macro [MFC]
- TN038
- BEGIN_INTERFACE_PART macro [MFC]
- DECLARE_INTERFACE_MAP macro [MFC]
- BEGIN_INTERFACE_MAP macro [MFC]
- OLE [MFC], implementing IUnknown interface
- METHOD_PROLOGUE macro [MFC]
- STDMETHOD macro [MFC]
- END_INTERFACE_PART macro [MFC]
- INTERFACE_PART macro
ms.assetid: 19d946ba-beaf-4881-85c6-0b598d7f6f11
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f6a52846754bdf1293e03a47127ae8886e0f1cd2
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952425"
---
# <a name="tn038-mfcole-iunknown-implementation"></a>TN038: Implementieren von MFC/OLE-IUnknown
> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Das Herzstück von OLE 2 ist das "OLE-Component Object Model" oder COM. COM definiert einen Standard für die Kommunikation kooperierender Objekte miteinander. Dazu gehören Details zum Aussehen eines "Objekts", einschließlich wie Methoden in einem Objekt weitergeleitet werden. COM definiert auch eine Basisklasse, von der alle COM-kompatiblen Klassen abgeleitet werden. Diese Basisklasse ist [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509). Obwohl der [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) -Schnittstelle als eine C++-Klasse bezeichnet wird, COM ist nicht spezifisch für alle eine Sprache – es kann in C, PASCAL oder einer beliebigen anderen Sprache, die das binäre Layout eines COM-Objekts unterstützen kann implementiert werden.  
  
 OLE verweist auf allen von abgeleiteten Klassen [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) als "Schnittstellen". Dies ist ein wichtiger Unterschied besteht darin, da eine "Schnittstelle" wie [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) keine Implementierung enthält. Sie definiert einfach das Protokoll, über das Objekte kommunizieren, nicht die speziellen Aufgaben dieser Implementierungen. Dies ist für ein System, das maximale Flexibilität zulässt, sinnvoll. Es ist die Aufgabe von MFC, ein Standardverhalten für MFC-/C++-Programme zu implementieren.  
  
 Um zu verstehen, die Implementierung von MFC [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) zuerst müssen Sie verstehen, was diese Schnittstelle ist. Eine vereinfachte Version des [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) wird unten definiert:  
  
```  
class IUnknown  
{  
public:  
    virtual HRESULT QueryInterface(REFIID iid, void** ppvObj) = 0;  
    virtual ULONG AddRef() = 0;  
    virtual ULONG Release() = 0;  
};  
```  
  
> [!NOTE]
>  Bestimmte erforderliche Aufrufkonventionsdetails, wie `__stdcall`, werden für diese Abbildung außer acht gelassen.  
  
 Die [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) und [Version](http://msdn.microsoft.com/library/windows/desktop/ms682317) Memberfunktionen steuern die Speicherverwaltung des Objekts. COM verwendet Verweiszählungsschema, um Objekte nachzuverfolgen. Auf ein Objekt wird nie direkt verwiesen wie in C++. Stattdessen wird auf COM-Objekte immer durch einen Zeiger verwiesen. Um das Objekt freizugeben, wenn der Besitzer ist verwenden, das Objekt des [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) Member aufgerufen (im Gegensatz zu mit Operators "Delete" wie für ein herkömmliches C++-Objekt). Dank des Verweiszählmechanismus können mehrere Verweise auf ein einzelnes Objekt verwaltet werden. Eine Implementierung der [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) und [Version](http://msdn.microsoft.com/library/windows/desktop/ms682317) verwaltet einen Verweiszähler für das Objekt – das Objekt wird nicht gelöscht werden, bis der entsprechende Verweiszähler 0 (null) erreicht.  
  
 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) und [Version](http://msdn.microsoft.com/library/windows/desktop/ms682317) sind aus Sicht der Implementierung recht einfach. Im Folgenden wird eine einfache Implementierung veranschaulicht:  
  
```  
ULONG CMyObj::AddRef()   
{   
    return ++m_dwRef;   
}  
 
ULONG CMyObj::Release()   
{   
    if (--m_dwRef == 0)   
 {  
    delete this;   
    return 0;  
 }  
    return m_dwRef;  
}  
```  
  
 Die [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) Memberfunktion ist etwas interessanter. Es ist nicht besonders interessant ein Objekt, dessen einzige Memberfunktionen sind [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) und [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) – es wäre schön, teilen Sie das Objekt, das als weitere erledigen [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) bietet. Dies ist, wenn [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) eignet. Sie ermöglicht Ihnen, eine andere "Schnittstelle" für dasselbe Objekt zu erhalten. Diese Schnittstellen werden in der Regel von abgeleitet [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) und zusätzliche Funktionen hinzufügen, indem neuen Memberfunktionen hinzugefügt. Für COM-Schnittstellen werden nie Membervariablen in der Schnittstelle deklariert, und alle Memberfunktionen werden als rein virtuell deklariert. Ein auf ein Objekt angewendeter  
  
```  
class IPrintInterface : public IUnknown  
{  
public:  
    virtual void PrintObject() = 0;  
};  
```  
  
 Ein iprintinterface-Objekt abgerufen, wenn Sie nur über eine [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), rufen Sie [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) mithilfe der `IID` von der `IPrintInterface`. Eine `IID` ist eine 128-Bit-Zahl, die die Schnittstelle eindeutig identifiziert. Für jede Schnittstelle gibt es eine `IID`, die entweder von Ihnen oder OLE definiert wird. Wenn *pUnk* ist ein Zeiger auf ein [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) Objekt möglicherweise der Code, um ein IPrintInterface daraus abzurufen:  
  
```  
IPrintInterface* pPrint = NULL;  
if (pUnk->QueryInterface(IID_IPrintInterface,   
 (void**)&pPrint) == NOERROR)  
{  
    pPrint->PrintObject();
pPrint->Release();
*// release pointer obtained via QueryInterface  
}  
```  
  
 Das erscheint recht einfach, aber wie würden Sie implementieren ein Objekt, das das iprintinterface-Objekt und [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) Schnittstelle In diesem Fall ist es einfach, da das iprintinterface-Objekt direkt von abgeleitetes [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) – durch Implementieren von IPrintInterface, [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) wird automatisch unterstützt. Zum Beispiel:  
  
```  
class CPrintObj : public CPrintInterface  
{  
    virtual HRESULT QueryInterface(REFIID iid, void** ppvObj);

    virtual ULONG AddRef();
virtual ULONG Release();
virtual void PrintObject();

};  
```  
  
 Die Implementierungen von [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) und [Version](http://msdn.microsoft.com/library/windows/desktop/ms682317) wären absolut identisch mit dieser implementierten oben. `CPrintObj::QueryInterface` Dies würde etwa wie folgt aussehen:  
  
```  
HRESULT CPrintObj::QueryInterface(REFIID iid, void FAR* FAR* ppvObj)  
{  
    if (iid == IID_IUnknown || iid == IID_IPrintInterface)  
 {  
 *ppvObj = this;  
    AddRef();
return NOERROR;  
 }  
    return E_NOINTERFACE;  
}  
```  
  
 Wenn der Schnittstellenbezeichner (IID) erkannt wird, wird ein Zeiger auf das Objekt zurückgegeben. Andernfalls tritt ein Fehler auf. Beachten Sie, dass ein erfolgreiches [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) führt zu einer impliziten [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379). Natürlich müssten Sie auch CEditObj::Print implementieren. Das ist einfach, da das iprintinterface-Objekt direkt abgeleitet wurde die [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) Schnittstelle. Jedoch, wenn Sie zwei unterschiedliche Schnittstellen unterstützen möchten, beide abgeleitet [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), berücksichtigen Sie Folgendes:  
  
```  
class IEditInterface : public IUnkown  
{  
public:  
    virtual void EditObject() = 0;  
};  
```  
  
 Obwohl es mehrere Möglichkeiten gibt, eine Klasse zu implementieren, die IEditInterface und IPrintInterface unterstützt, einschließlich Verwenden der C++-Mehrfachvererbung, konzentriert sich dieser Hinweis auf die Verwendung von geschachtelten Klassen zur Implementierung dieser Funktionalität.  
  
```  
class CEditPrintObj  
{  
public:  
    CEditPrintObj();

 
    HRESULT QueryInterface(REFIID iid,
    void**);

    ULONG AddRef();
ULONG Release();
DWORD m_dwRef;  
 
    class CPrintObj : public IPrintInterface  
 {  
    public: 
    CEditPrintObj* m_pParent;  
    virtual HRESULT QueryInterface(REFIID iid,
    void** ppvObj);

    virtual ULONG AddRef();
virtual ULONG Release();

 } m_printObj;  
 
    class CEditObj : public IEditInterface  
 {  
    public: 
    CEditPrintObj* m_pParent;  
    virtual ULONG QueryInterface(REFIID iid,
    void** ppvObj);

    virtual ULONG AddRef();
virtual ULONG Release();

 } m_editObj;  
};  
```  
  
 Die gesamte Implementierung wird unten aufgeführt:  
  
```  
CEditPrintObj::CEditPrintObj()  
{  
    m_editObj.m_pParent = this;  
    m_printObj.m_pParent = this;  
}  
 
ULONG CEditPrintObj::AddRef()   
{   
    return ++m_dwRef;  
}  
 
CEditPrintObj::Release()  
{  
    if (--m_dwRef == 0)  
 {  
    delete this;  
    return 0;  
 }  
    return m_dwRef;  
}  
 
HRESULT CEditPrintObj::QueryInterface(REFIID iid,
    void** ppvObj)  
{  
    if (iid == IID_IUnknown || iid == IID_IPrintInterface)  
 {  
 *ppvObj = &m_printObj;  
    AddRef();
return NOERROR;  
 }  
    else if (iid == IID_IEditInterface)  
 {  
 *ppvObj = &m_editObj;  
    AddRef();
return NOERROR;  
 }  
    return E_NOINTERFACE;  
}  
 
ULONG CEditPrintObj::CEditObj::AddRef()   
{   
    return m_pParent->AddRef();

}  
 
ULONG CEditPrintObj::CEditObj::Release()   
{   
    return m_pParent->Release();

}  
 
HRESULT CEditPrintObj::CEditObj::QueryInterface(
    REFIID iid,
    void** ppvObj)   
{   
    return m_pParent->QueryInterface(iid,
    ppvObj);

}  
 
ULONG CEditPrintObj::CPrintObj::AddRef()   
{   
    return m_pParent->AddRef();

}  
 
ULONG CEditPrintObj::CPrintObj::Release()   
{   
    return m_pParent->Release();

}  
 
HRESULT CEditPrintObj::CPrintObj::QueryInterface(
    REFIID iid,
    void** ppvObj)   
{   
    return m_pParent->QueryInterface(iid,
    ppvObj);

}  
```  
  
 Beachten Sie, dass ein Großteil der [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) Implementierung befindet sich in die CEditPrintObj-Klasse statt den Code in ceditprintobj:: Ceditobj und cprintobj zu duplizieren. So wird die Codemenge reduziert und Fehler vermieden. Wichtig ist, dass von der IUnknown-Schnittstelle es möglich ist, rufen Sie [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) zum Abrufen einer beliebigen Schnittstelle unterstützen jedoch stattdessen das und aus jeder dieser Schnittstellen ist es möglich, diesen Vorgang auszuführen. Dies bedeutet, dass alle [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) Funktionen, die von den einzelnen Schnittstellen verfügbar sind, müssen genau die gleiche Weise Verhalten. Damit diese eingebetteten Objekte die Implementierung im "äußeren Objekt" aufrufen kann, wird ein Gegenzeiger verwendet (m_pParent). Der m_pParent-Zeiger wird während des CEditPrintObj-Konstruktors initialisiert. Anschließend würden Sie CEditPrintObj::CPrintObj::PrintObject und CEditPrintObj::CEditObj::EditObject ebenfalls implementieren. Es wurde relativ viel Code für eine Funktion, die Fähigkeit zum Bearbeiten des Objekts, hinzugefügt. Glücklicherweise ist es recht selten, dass Schnittstellen nur über eine einzelne Memberfunktion verfügen (es kann jedoch durchaus vorkommen) und in diesem Fall würden EditObject und PrintObject normalerweise zu einer einzelnen Schnittstelle kombiniert werden.  
  
 Das ist eine umfassende Erläuterung und viel Code für ein solch einfaches Szenario. Die MFC/OLE-Klassen stellen eine einfachere Alternative zur Verfügung. Die MFC-Implementierung verwendet eine Technik, die mit der Methode vergleichbar ist, mit der Windows-Meldungen mit Meldungszuordnungen umschlossen werden. Diese Funktion wird aufgerufen, *Schnittstellenzuordnungen* und wird im nächsten Abschnitt erläutert.  
  
## <a name="mfc-interface-maps"></a>MFC-Schnittstellenzuordnungen  
 MFC/OLE beinhaltet die Implementierung von "Schnittstellenzuordnungen", die in Bezug auf Konzept und in der Ausführung den "Meldungszuordnungen" und "Dispatchzuordnungen" von MFC ähneln. Die Kernfunktionen der Schnittstellenzuordnungen von MFC sind folgende:  
  
-   Eine Standardimplementierung von [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), integriert der `CCmdTarget` Klasse.  
  
-   Wartung des Verweiszählers, geändert von [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) und [Version](http://msdn.microsoft.com/library/windows/desktop/ms682317)  
  
-   Datengesteuerte Implementierung von [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)  
  
 Außerdem unterstützen Schnittstellenzuordnungen die folgenden erweiterten Funktionen:  
  
-   Unterstützung für das Erstellen von aggregatfähigen COM-Objekten  
  
-   Unterstützung für das Verwenden von aggregierten Objekten in der Implementierung eines COM-Objekts  
  
-   Die Implementierung ist "hookable" und erweiterbar  
  
 Weitere Informationen zum Aggregieren finden Sie unter der [Aggregation](http://msdn.microsoft.com/library/windows/desktop/ms686558\(v=vs.85\).aspx) Thema.  
  
 Die Unterstützung der Schnittstellenzuordnung von MFC haben ihren Stammpfad in der `CCmdTarget`-Klasse. `CCmdTarget` "*verfügt über eine*" Verweiszähler sowie alle die Memberfunktionen zugeordneten verweisen die [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) Implementierung (der Verweiszähler ist beispielsweise `CCmdTarget`). Um eine Klasse zu erstellen, die OLE-COM unterstützt, leiten Sie eine Klasse von `CCmdTarget` ab, und verwenden Sie verschiedene Makros sowie Memberfunktionen von `CCmdTarget`, um die gewünschten Schnittstellen zu implementieren. Die Implementierung von MFC verwendet geschachtelte Klassen, um die jeweilige Schnittstellenimplementierung ähnlich wie im Beispiel oben zu definieren. Dies wird mit einer Standardimplementierung von IUnknown sowie mit einer Reihe von Makros erleichtert, durch die ein Teil des sich wiederholenden Codes entfällt.  
  
## <a name="interface-map-basics"></a>Grundlagen zu Schnittstellenzuordnungen  
  
#### <a name="to-implement-a-class-using-mfcs-interface-maps"></a>So implementieren Sie eine Klasse mithilfe der Schnittstellenzuordnungen von MFC  
  
1.  Leiten Sie eine Klasse entweder direkt oder indirekt von `CCmdTarget` ab.  
  
2.  Verwenden Sie die `DECLARE_INTERFACE_MAP`-Function in der abgeleiteten Klassendefinition.  
  
3.  Verwenden Sie für jede Schnittstelle, die Sie unterstützen möchten, die BEGIN_INTERFACE_PART und END_INTERFACE_PART Makros in der Klassendefinition ein.  
  
4.  Verwenden Sie in der Implementierungsdatei die Makros BEGIN_INTERFACE_MAP und END_INTERFACE_MAP schnittstellenzuordnung der Klasse zu definieren.  
  
5.  Verwenden Sie für jede unterstützte IID das INTERFACE_PART-Makro zwischen den BEGIN_INTERFACE_MAP und END_INTERFACE_MAP-Makros, um diese IID einem bestimmten "Teil" der Klasse zuordnen.  
  
6.  Implementieren Sie die geschachtelten Klassen, die die von Ihnen unterstützten Schnittstellen darstellen.  
  
7.  Verwenden Sie das METHOD_PROLOGUE-Makro auf das übergeordnete Element `CCmdTarget`-abgeleitetes Objekt.  
  
8. [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317), und [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) können zum Delegieren der `CCmdTarget` Implementierung dieser Funktionen (`ExternalAddRef`, `ExternalRelease`, und `ExternalQueryInterface`).  
  
 Das obige CPrintEditObj-Beispiel kann implementiert wie folgt werden:  
  
```  
class CPrintEditObj : public CCmdTarget  
{  
public: *// member data and member functions for CPrintEditObj go here  
 
// Interface Maps  
protected:  
    DECLARE_INTERFACE_MAP() 
 
    BEGIN_INTERFACE_PART(EditObj,
    IEditInterface)  
    STDMETHOD_(void,
    EditObject)();
END_INTERFACE_PART(EditObj) 
 
    BEGIN_INTERFACE_PART(PrintObj,
    IPrintInterface)  
    STDMETHOD_(void,
    PrintObject)();
END_INTERFACE_PART(PrintObj) 
};  
```  
  
 Die obige Deklaration erstellt eine Klasse, die von `CCmdTarget` abgeleitet wird. DECLARE_INTERFACE_MAP-Makro mitgeteilt, dass diese Klasse eine benutzerdefinierte schnittstellenzuordnung hat. Darüber hinaus definieren die Makros BEGIN_INTERFACE_PART und END_INTERFACE_PART geschachtelte Klassen in diesem Fall mit Namen CEditObj und CPrintObj (das "X" wird nur verwendet, um die geschachtelten Klassen von globalen Klassen zu unterscheiden, beginnen mit "C" und die Schnittstelle der Klassen beginnen Sie mit "I"). Zwei geschachtelte Member dieser Klassen werden erstellt: m_CEditObj bzw. m_CPrintObj. Die Makros deklarieren automatisch die [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317), und [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) Funktionen; daher deklarieren Sie nur die Funktionen speziell für diese Schnittstelle: EditObject und PrintObject (das OLE-Makro STDMETHOD wird verwendet, damit **_stdcall** und virtuelle Schlüsselwörter nach Bedarf für die Zielplattform bereitgestellt werden).  
  
 So implementieren Sie Schnittstellenzuordnung für diese Klasse:  
  
```  
BEGIN_INTERFACE_MAP(CPrintEditObj,
    CCmdTarget)  
    INTERFACE_PART(CPrintEditObj,
    IID_IPrintInterface,
    PrintObj)  
    INTERFACE_PART(CPrintEditObj,
    IID_IEditInterface,
    EditObj)  
END_INTERFACE_MAP()  
```  
  
 Damit wird die IID "IID_IPrintInterface" mit "m_CPrintObj" und "IID_IEditInterface" mit "m_CEditObj" verbunden. Die `CCmdTarget` Implementierung von [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) (`CCmdTarget::ExternalQueryInterface`) verwendet diese Zuordnung zurückzugebenden Zeiger "m_cprintobj" und "m_ceditobj" verbunden, wenn angefordert. Es ist nicht erforderlich, einen Eintrag für `IID_IUnknown` einzuschließen. Das Framework verwendet die erste Schnittstelle in der Zuordnung (in diesem Fall "m_CPrintObj"), wenn `IID_IUnknown` angefordert wird.  
  
 Obwohl das BEGIN_INTERFACE_PART-Makro automatisch deklariert die [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) und [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) Funktionen müssen Sie sie implementieren:  
  
```  
ULONG FAR EXPORT CEditPrintObj::XEditObj::AddRef()  
{  
    METHOD_PROLOGUE(CEditPrintObj,
    EditObj)  
    return pThis->ExternalAddRef();

}  
 
ULONG FAR EXPORT CEditPrintObj::XEditObj::Release()  
{  
    METHOD_PROLOGUE(CEditPrintObj,
    EditObj)  
    return pThis->ExternalRelease();

}  
 
HRESULT FAR EXPORT CEditPrintObj::XEditObj::QueryInterface(
    REFIID iid,
    void FAR* FAR* ppvObj)  
{  
    METHOD_PROLOGUE(CEditPrintObj,
    EditObj)  
    return (HRESULT)pThis->ExternalQueryInterface(&iid,
    ppvObj);

}  
 
void FAR EXPORT CEditPrintObj::XEditObj::EditObject()  
{  
    METHOD_PROLOGUE(CEditPrintObj,
    EditObj) *// code to "Edit" the object,
    whatever that means...  
}  
```  
  
 Die Implementierung für CEditPrintObj::CPrintObj entspricht weitgehend den oben beschriebenen Definitionen für CEditPrintObj::CEditObj. Obwohl es möglich wäre, ein Makro zu erstellen, mit dem diese Funktionen automatisch generiert werden (was am Anfang der MFC/OLE-Entwicklung der Fall war), wird es schwierig, Haltepunkte festzulegen, wenn ein Makro mehrere Codezeilen generiert. Aus diesem Grund wird dieser Code manuell erweitert.  
  
 Durch Verwendung der Frameworkimplementierung von Meldungszuordnungen mussten einige Vorgänge nicht ausgeführt werden:  
  
-   Implementieren von QueryInterface  
  
-   Implementieren von AddRef und Release  
  
-   Deklarieren eine dieser integrierten Methoden auf beiden Schnittstellen  
  
 Darüber hinaus verwendet das Framework Meldungszuordnungen intern. So können Sie aus einer Frameworkklasse ableiten, beispielsweise `COleServerDoc`, die bereits bestimmte Schnittstellen unterstützt und entweder Ersatz oder Hinzufügungen zu den Schnittstellen bereitstellt, die im Framework enthalten sind. Dies ist möglich, da das Framework das Erben einer Schnittstellenzuordnung von einer Basisklasse vollständig unterstützt. Das ist der Grund, warum BEGIN_INTERFACE_MAP als zweiten Parameter den Namen der Basisklasse behandelt.  
  
> [!NOTE]
>  Es ist im Allgemeinen nicht möglich, die Implementierung der integrierten MFC-Implementierungen der OLE-Schnittstellen nur durch Vererben der eingebetteten Spezialisierung dieser Schnittstelle von der MFC-Version wiederzuverwenden. Dies ist nicht möglich da die Verwendung von der METHOD_PROLOGUE-Makro für den Zugriff auf das enthaltende `CCmdTarget`-abgeleiteten Objekts impliziert einen *festen Offset* des eingebetteten Objekts aus der `CCmdTarget`-abgeleitetes Objekt. Dies bedeutet z. B., dass Sie kein eingebettetes XMyAdviseSink von der MFC-Implementierung in `COleClientItem::XAdviseSink` ableiten können, da XAdviseSink sich an einem bestimmten Offset oben im `COleClientItem`-Objekt befinden muss.  
  
> [!NOTE]
>  Sie können alle Funktionen, für die das Standardverhalten von MFC gelten soll, jedoch an die MFC-Implementierung delegieren. Dies wird in der MFC-Implementierung von `IOleInPlaceFrame` (XOleInPlaceFrame) in der `COleFrameHook`-Klasse ausgeführt (sie delegiert viele Funktionen zu m_xOleInPlaceUIWindow). Dieser Entwurf wurde ausgewählt, um die Laufzeitgröße von Objekten zu reduzieren, die viele Schnittstellen implementieren. Mit diesem Entwurf ist kein Gegenzeiger mehr erforderlich (wie bei Verwendung von m_pParent im vorherigen Abschnitt).  
  
### <a name="aggregation-and-interface-maps"></a>Aggregation und Schnittstellenzuordnungen  
 Zusätzlich zur Unterstützung von eigenständigen COM-Objekten unterstützt MFC auch Aggregation. Aggregation an sich ist zu komplex eines Themas, finden Sie im; finden Sie in der [Aggregation](http://msdn.microsoft.com/library/windows/desktop/ms686558\(v=vs.85\).aspx) Thema für Weitere Informationen zum Aggregieren. Dieser Hinweis beschreibt einfach die Unterstützung für die Aggregation, die in den Framework und die Schnittstellenzuordnungen integriert ist.  
  
 Es gibt zwei Möglichkeiten, Aggregation zu verwenden: (1) mit einem COM-Objekt, das Aggregation unterstützt und (2) durch Implementierung eines Objekts, von einem anderen aggregiert werden kann. Diese Funktionen können als "Verwenden eines Aggregatobjekts" und "Ausstatten einer Objekt-Implementierung mit Aggregatfähigkeit" bezeichnet werden. MFC unterstützt beide Funktionen.  
  
### <a name="using-an-aggregate-object"></a>Verwenden eines Aggregatobjekts  
 Zur Verwendung eines Aggregatobjekts, muss es eine Methode geben, um das Aggregat in den QueryInterface-Mechanismus einzubinden. Das heißt, das Aggregatobjekt muss sich wie ein systemeigener Teil des Objekts verhalten. Wie wird dieser Tie in MFC schnittstellenzuordnungsmechanismus zusätzlich zu den INTERFACE_PART-Makro, wobei ein geschachteltes Objekt einer IID zugeordnet ist, können Sie auch deklarieren ein aggregatobjekts als Teil Ihrer `CCmdTarget` abgeleitete Klasse. Zu diesem Zweck dient das INTERFACE_AGGREGATE-Makro. Dadurch können Sie eine Membervariable anzugeben (die muss ein Zeiger auf ein [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) oder eine abgeleitete Klasse), also in den schnittstellenzuordnungsmechanismus integriert werden. Sollte der Zeiger nicht NULL bei `CCmdTarget::ExternalQueryInterface` wird aufgerufen, ruft das Framework automatisch des aggregatobjekts [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) Memberfunktion, wenn die `IID` angefordert ist keiner der systemeigenen `IID`s unterstützt durch die `CCmdTarget` Objekt selbst.  
  
##### <a name="to-use-the-interfaceaggregate-macro"></a>So verwenden Sie das INTERFACE_AGGREGATE-Makro  
  
1.  Deklarieren Sie eine Membervariable (`IUnknown*`), die einen Zeiger auf das Aggregatobjekt enthält.  
  
2.  Schließen Sie ein INTERFACE_AGGREGATE-Makro in die schnittstellenzuordnung, bezieht sich auf die Membervariable anhand des Namens.  
  
3.  Daraufhin (normalerweise während `CCmdTarget::OnCreateAggregates`) initialisieren Sie die Membervariable auf einen anderen Wert als NULL.  
  
 Zum Beispiel:  
  
```  
class CAggrExample : public CCmdTarget  
{  
public:  
    CAggrExample();

 
protected:  
    LPUNKNOWN m_lpAggrInner;  
    virtual BOOL OnCreateAggregates();

 
    DECLARE_INTERFACE_MAP() *// "native" interface part macros may be used here  
};  
 
CAggrExample::CAggrExample()  
{  
    m_lpAggrInner = NULL;  
}  
 
BOOL CAggrExample::OnCreateAggregates()  
{ *// wire up aggregate with correct controlling unknown  
    m_lpAggrInner = CoCreateInstance(CLSID_Example,  
    GetControllingUnknown(),
    CLSCTX_INPROC_SERVER,  
    IID_IUnknown, (LPVOID*)&m_lpAggrInner);

    if (m_lpAggrInner == NULL)  
    return FALSE; *// optionally,
    create other aggregate objects here  
    return TRUE;  
}  
 
BEGIN_INTERFACE_MAP(CAggrExample,
    CCmdTarget) *// native "INTERFACE_PART" entries go here  
    INTERFACE_AGGREGATE(CAggrExample,
    m_lpAggrInner)  
END_INTERFACE_MAP()  
```  
  
 Die m_lpAggrInner-Variable wird im Konstruktor auf NULL initialisiert. Das Framework ignoriert eine Membervariable NULL in die standardmäßige Implementierung des [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521). Das `OnCreateAggregates`-Objekt eignet sich gut, um die Aggregatobjekte tatsächlich zu erstellen. Sie müssen dieses Objekt explizit aufrufen, wenn Sie das Objekt außerhalb der MFC-Implementierung von `COleObjectFactory` erstellen. Der Grund für das Erstellen von Aggregaten in `CCmdTarget::OnCreateAggregates` und die Verwendung von `CCmdTarget::GetControllingUnknown` wird offensichtlich, wenn das Erstellen von aggregatfähigen Objekten erläutert wird.  
  
 Mit dieser Methode erhält das Objekt alle Schnittstellen, die das Aggregatobjekt unterstützt, sowie deren systemeigene Schnittstellen. Wenn Sie nur eine Teilmenge der Schnittstellen benötigen, die das Aggregat unterstützt, können Sie `CCmdTarget::GetInterfaceHook` überschreiben. Dadurch können Sie sehr niedrigen Ebene Hookability, ähnlich wie [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521). Normalerweise werden alle Schnittstellen gewünscht, die das Aggregat unterstützt.  
  
### <a name="making-an-object-implementation-aggregatable"></a>Ausstatten einer Objekt-Implementierung mit Aggregationsfähigkeit  
 Für ein Objekt aggregatfähig, die Implementierung von [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317), und [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) delegieren muss, um ein "controlling Unknown". Das heißt, dass es als Teil des Objekts, delegieren muss [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317), und [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) auch an ein anderes Objekt abgeleitet [ IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509). Dieses "controlling unknown"-Objekt wird dem Objekt beim Erstellen zur Verfügung gestellt, d. h., es wird der Implementierung von `COleObjectFactory` bereitgestellt. Das Implementieren bedeutet einen geringen Mehraufwand, und in einigen Fällen ist es nicht wünschenswert, sodass dies laut MFC optional ist. Um ein Objekt aggregatfähig zu machen, rufen Sie `CCmdTarget::EnableAggregation` im Konstruktor des Objekts auf.  
  
 Wenn das Objekt auch Aggregate verwendet, müssen Sie zudem sicherstellen, das richtige "controlling unknown"-Objekt an die Aggregatobjekte zu übergeben. Normalerweise wird dieser [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) -Zeiger an das Objekt übergeben wird, wenn das Aggregat erstellt wird. Beispielsweise ist der pUnkOuter-Parameter der "controlling unknown"-Zeiger für Objekte, die mit `CoCreateInstance` erstellt werden. Der richtige "controlling unknown"-Zeiger kann durch Aufrufen von `CCmdTarget::GetControllingUnknown` abgerufen werden. Der Wert, der von dieser Funktion zurückgegeben wird, ist jedoch während des Konstruktors ungültig. Aus diesem Grund wird vorgeschlagen, die Aggregate nur in einer Überschreibung von `CCmdTarget::OnCreateAggregates` zu erstellen, bei der der Rückgabewert von `GetControllingUnknown` zuverlässig ist, auch wenn er von der `COleObjectFactory`-Implementierung erstellt wird.  
  
 Wichtig ist auch, dass das Objekt den richtigen Verweiszähler bearbeitet, wenn künstliche Verweiszähler hinzugefügt oder freigegeben werden. Um dies sicherzustellen, rufen Sie immer `ExternalAddRef` und `ExternalRelease` statt `InternalRelease` und `InternalAddRef` auf. Es passiert nur selten, dass `InternalRelease` oder `InternalAddRef` für eine Klasse aufgerufen werden, die Aggregation unterstützt.  
  
### <a name="reference-material"></a>Referenzmaterial  
 Die erweiterte Verwendung von OLE, wie Definieren eigener Schnittstellen oder Überschreiben der Implementierung des Frameworks der OLE-Schnittstellen, erfordert die Nutzung des zugrunde liegenden Schnittstellenzuordnungsmechanismus.  
  
 In diesem Abschnitt werden alle Makros und APIs erläutert, die zum Implementieren dieser erweiterten Funktionen verwendet werden.  
  
### <a name="ccmdtargetenableaggregation--function-description"></a>CCmdTarget::EnableAggregation – Funktionsbeschreibung  
  
```  
 
void EnableAggregation();

 
```  
  
## <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion im Konstruktor der abgeleiteten Klasse auf, wenn Sie OLE-Aggregation für Objekte dieses Typs unterstützen möchten. Dadurch wird eine besondere IUnknown-Implementierung vorbereitet, die für aggregatfähige Objekte erforderlich ist.  
  
### <a name="ccmdtargetexternalqueryinterface--function-description"></a>CCmdTarget::ExternalQueryInterface – Funktionsbeschreibung  
  
```  
 
    DWORD ExternalQueryInterface(constvoidFAR* lpIID, LPVOIDFAR* ppvObj);
```  
  
## <a name="remarks"></a>Hinweise  
  
#### <a name="parameters"></a>Parameter  
 *lpIID*  
 Ein ferner Zeiger auf eine IID (das erste Argument für QueryInterface)  
  
 *ppvObj*  
 Ein Zeiger auf ein IUnknown*-Objekt (das zweite Argument für QueryInterface)  
  
## <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion in der Implementierung von IUnknown für jede Schnittstelle auf, die Ihre Klasse implementiert. Diese Funktion stellt die datengesteuerte Standardimplementierung von QueryInterface auf Grundlage der Schnittstellenzuordnung des Objekts bereit. Es ist erforderlich, den Rückgabewert in ein HRESULT umzuwandeln. Wenn das Objekt aggregiert wird, ruft diese Funktion das "controlling IUnknown"-Objekt auf, anstatt die lokale Schnittstellenzuordnung zu verwenden.  
  
### <a name="ccmdtargetexternaladdref--function-description"></a>CCmdTarget::ExternalAddRef – Funktionsbeschreibung  
  
```  
 
DWORD ExternalAddRef();

 
```  
  
## <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion in der Implementierung von IUnknown::AddRef für jede Schnittstelle auf, die Ihre Klasse implementiert. Der Rückgabewert ist der neue Verweiszähler für das CCmdTarget-Objekt. Wenn das Objekt aggregiert wird, ruft diese Funktion das "controlling IUnknown"-Objekt auf, anstatt den lokalen Verweiszähler zu bearbeiten.  
  
### <a name="ccmdtargetexternalrelease--function-description"></a>CCmdTarget::ExternalRelease – Funktionsbeschreibung  
  
```  
 
DWORD ExternalRelease();

 
```  
  
## <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion in der Implementierung von IUnknown::Release für jede Schnittstelle auf, die Ihre Klasse implementiert. Der Rückgabewert gibt den neuen Verweiszähler für das Objekt an. Wenn das Objekt aggregiert wird, ruft diese Funktion das "controlling IUnknown"-Objekt auf, anstatt den lokalen Verweiszähler zu bearbeiten.  
  
### <a name="declareinterfacemap--macro-description"></a>DECLARE_INTERFACE_MAP – Makrobeschreibung  
  
```  
 
DECLARE_INTERFACE_MAP  
 
```  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro in einer Klasse, die von `CCmdTarget` abgeleitet ist und über eine Schnittstellenzuordnung verfügt. Verwendet im Wesentlichen die gleiche Weise wie DECLARE_MESSAGE_MAP. Dieser Makroaufruf sollte in die Klassendefinition, normalerweise in einer Headerdatei (.H), platziert werden. Eine Klasse mit DECLARE_INTERFACE_MAP muss die schnittstellenzuordnung definieren, in der Implementierungsdatei (. CPP) mit den Makros BEGIN_INTERFACE_MAP und END_INTERFACE_MAP.  
  
### <a name="begininterfacepart-and-endinterfacepart--macro-descriptions"></a>BEGIN_INTERFACE_PART und END_INTERFACE_PART – Makrobeschreibungen  
  
```  
 
    BEGIN_INTERFACE_PART(
 localClass,   
    iface);

END_INTERFACE_PART(
 localClass)  
```  
  
## <a name="remarks"></a>Hinweise  
  
#### <a name="parameters"></a>Parameter  
 *localClass*  
 Der Name der Klasse, die die Schnittstelle implementiert  
  
 *iface*  
 Der Name der Schnittstelle, die diese Klasse implementiert  
  
## <a name="remarks"></a>Hinweise  
 Für jede Schnittstelle, die Ihre Klasse implementiert werden sollen, müssen Sie ein paar BEGIN_INTERFACE_PART und END_INTERFACE_PART haben. Diese Makros definieren eine lokale Klasse, die von der von Ihnen definierten OLE-Schnittstelle abgeleitet wird, sowie eine eingebettete Membervariable dieser Klasse. Die [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317), und [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) Elemente werden automatisch deklariert. Sie müssen die Deklarationen für die anderen Memberfunktionen, die Teil der implementierten Schnittstelle einschließen (diese Deklarationen werden zwischen die Makros BEGIN_INTERFACE_PART und END_INTERFACE_PART platziert).  
  
 Die *Iface* Argument ist die OLE-Schnittstelle, die Sie implementieren, z. B. möchten `IAdviseSink`, oder `IPersistStorage` (oder eine eigene benutzerdefinierte Schnittstelle).  
  
 Die *LocalClass* -Argument ist der Name der lokalen Klasse, die definiert wird. Der Buchstabe "x" wird dem Namen automatisch vorangestellt. Diese Namenskonvention wird verwendet, um Konflikte mit gleichnamigen globalen Klassen zu vermeiden. Darüber hinaus den Namen des eingebetteten Members, identisch mit der *LocalClass* nennen, außer es "M_x" vorangestellt ist.  
  
 Zum Beispiel:  
  
```  
BEGIN_INTERFACE_PART(MyAdviseSink,
    IAdviseSink)  
    STDMETHOD_(void,
    OnDataChange)(LPFORMATETC,
    LPSTGMEDIUM);

    STDMETHOD_(void,
    OnViewChange)(DWORD,
    LONG);

    STDMETHOD_(void,
    OnRename)(LPMONIKER);

 STDMETHOD_(void,
    OnSave)();
STDMETHOD_(void,
    OnClose)();

END_INTERFACE_PART(MyAdviseSink) 
```  
  
 würde eine lokale Klasse mit dem Namen XMyAdviseSink definieren, der von IAdviseSink abgeleitet wurde, und ein Member der Klasse, in der es als m_xMyAdviseSink.Note deklariert wird:  
  
> [!NOTE]
>  Die Zeilen ab `STDMETHOD`_ im Wesentlichen aus OLE2 kopiert werden. H und geringfügig geändert. Durch Kopieren aus OLE2.H lassen sich Fehler reduzieren, die andernfalls schwer zu beheben sind.  
  
### <a name="begininterfacemap-and-endinterfacemap--macro-descriptions"></a>BEGIN_INTERFACE_MAP und END_INTERFACE_MAP – Makrobeschreibungen  
  
```  
 
    BEGIN_INTERFACE_MAP(
 theClass,   
    baseClass)END_INTERFACE_MAP 
```  
  
## <a name="remarks"></a>Hinweise  
  
#### <a name="parameters"></a>Parameter  
 *theClass*  
 Die Klasse, in der die Schnittstellenzuordnung definiert werden soll  
  
 *baseClass*  
 Die Klasse, von der *TheClass* abgeleitet.  
  
## <a name="remarks"></a>Hinweise  
 BEGIN_INTERFACE_MAP und END_INTERFACE_MAP Makros werden in der Implementierungsdatei verwendet, um die schnittstellenzuordnung tatsächlich zu definieren. Es gibt eine oder mehrere Aufrufe von INTERFACE_PART-Makro, für jede Schnittstelle, die implementiert wird. Für jedes Aggregat, das die Klasse verwendet wird, ist eine INTERFACE_AGGREGATE-Makro-Aufruf.  
  
### <a name="interfacepart--macro-description"></a>INTERFACE_PART – Makrobeschreibung  
  
```  
 
    INTERFACE_PART(
 theClass,   
    iid, 
    localClass) 
```  
  
## <a name="remarks"></a>Hinweise  
  
#### <a name="parameters"></a>Parameter  
 *theClass*  
 Der Name der Klasse, die die Schnittstellenzuordnung enthält.  
  
 *IID*  
 Die `IID`, die der eingebetteten Klasse zugeordnet werden soll.  
  
 *localClass*  
 Der Name der lokalen Klasse (ohne das "X").  
  
## <a name="remarks"></a>Hinweise  
 Dieses Makro wird zwischen das Makro BEGIN_INTERFACE_MAP und END_INTERFACE_MAP-Makro für jede Schnittstelle verwendet, die das Objekt unterstützt werden. Sie können Sie eine IID auf einen Member der Klasse, die durch zuordnen *TheClass* und *LocalClass*. Das "M_x" werden hinzugefügt werden, um die *LocalClass* automatisch. Beachten Sie, dass maximal eine `IID` mit einem einzigen Member zugeordnet werden kann. Dies ist hilfreich, wenn Sie nur eine "am stärksten abgeleitete" Schnittstelle implementieren und alle Zwischenschnittstellen ebenfalls bereitstellen möchten. Ein gutes Beispiel hierfür ist die `IOleInPlaceFrameWindow`-Schnittstelle. Die Hierarchie sieht wie folgt aus:  
  
```  
IUnknown  
    IOleWindow 
    IOleUIWindow 
    IOleInPlaceFrameWindow 
```  
  
 Wenn ein Objekt implementiert `IOleInPlaceFrameWindow`, kann ein Client `QueryInterface` auf den folgenden Schnittstellen: `IOleUIWindow`, `IOleWindow`, oder [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), außer "am stärksten abgeleiteten" Schnittstelle `IOleInPlaceFrameWindow` (derjenige Sie befinden sich nämlich implementieren). In diesem Fall können Sie mehrere INTERFACE_PART-Makro jede mögliche Basisschnittstelle zum Zuordnen der `IOleInPlaceFrameWindow` Schnittstelle:  
  
 in der Klassendefinitionsdatei:  
  
```  
BEGIN_INTERFACE_PART(CMyFrameWindow, IOleInPlaceFrameWindow)  
```  
  
 in der Klassenimplementierungsdatei:  
  
```  
BEGIN_INTERFACE_MAP(CMyWnd,
    CFrameWnd)  
    INTERFACE_PART(CMyWnd,
    IID_IOleWindow,
    MyFrameWindow)  
    INTERFACE_PART(CMyWnd,
    IID_IOleUIWindow,
    MyFrameWindow)  
    INTERFACE_PART(CMyWnd,
    IID_IOleInPlaceFrameWindow,
    MyFrameWindow)  
END_INTERFACE_MAP  
```  
  
 Das Framework berücksichtigt IUnknown, da es immer erforderlich ist.  
  
### <a name="interfacepart--macro-description"></a>INTERFACE_PART – Makrobeschreibung  
  
```  
 
    INTERFACE_AGGREGATE(
 theClass,   
    theAggr) 
```  
  
## <a name="remarks"></a>Hinweise  
  
#### <a name="parameters"></a>Parameter  
 *theClass*  
 Der Name der Klasse, die die Schnittstellenzuordnung enthält,  
  
 *theAggr*  
 Der Name der Membervariable, die aggregiert werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Dieses Makro wird verwendet, um dem Framework mitzuteilen, dass die Klasse ein Aggregatobjekt verwendet. Es muss zwischen die Makros BEGIN_INTERFACE_PART und END_INTERFACE_PART angezeigt werden. Ein Aggregatobjekt ist ein separates Objekt abgeleitet [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509). Ein Aggregat und das INTERFACE_AGGREGATE-Makro verwenden, können Sie alle Schnittstellen vornehmen, die vom Aggregat unterstützt angezeigt werden, von dem Objekt direkt unterstützt werden müssen. Die *TheAggr* Argument ist einfach der Name einer Membervariable der Klasse, die abgeleitet ist [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) (entweder direkt oder indirekt). Alle INTERFACE_AGGREGATE-Makros folgen INTERFACE_PART-Makros, wenn in eine schnittstellenzuordnung eingefügt.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

