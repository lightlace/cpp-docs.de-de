---
title: "TN038: Implementieren von MFC/OLE-IUnknown | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Aggregationsmakros [C++]"
  - "BEGIN_INTERFACE_MAP-Makro"
  - "BEGIN_INTERFACE_PART-Makro"
  - "COM-Schnittstellen, Basisschnittstelle"
  - "DECLARE_INTERFACE_MAP-Makro"
  - "END_INTERFACE_MAP-Makro"
  - "END_INTERFACE_PART-Makro"
  - "INTERFACE_PART-Makro"
  - "IUnknown-Schnittstelle"
  - "METHOD_PROLOGUE-Makro"
  - "OLE [C++], Implementieren der IUnknown-Schnittstelle"
  - "STDMETHOD-Makro"
  - "TN038"
ms.assetid: 19d946ba-beaf-4881-85c6-0b598d7f6f11
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# TN038: Implementieren von MFC/OLE-IUnknown
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert.  Daher können einige Verfahren und Themen veraltet oder falsch sein.  Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Das Herzstück von OLE 2 ist das "OLE\-Component Object Model" oder COM.  COM definiert einen Standard für die Kommunikation kooperierender Objekte miteinander.  Dazu gehören Details zum Aussehen eines "Objekts", einschließlich wie Methoden in einem Objekt weitergeleitet werden.  COM definiert auch eine Basisklasse, von der alle COM\-kompatiblen Klassen abgeleitet werden.  Diese Basisklasse ist [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509).  Obwohl die [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)\-Schnittstelle als eine C\+\+\-Klasse bezeichnet wird, bezieht sich COM nicht auf eine bestimmte Sprache. Es kann C, PASCAL oder einer beliebigen anderen Sprache implementiert werden, die das binäre Layout eines COM\-Objekts unterstützen kann.  
  
 OLE verweist auf alle Klassen, die von [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) als "Schnittstellen" abgeleitet werden. Dies ist ein wichtiger Unterschied, da eine "Schnittstelle" wie [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) keine Implementierung enthält.  Sie definiert einfach das Protokoll, über das Objekte kommunizieren, nicht die speziellen Aufgaben dieser Implementierungen.  Dies ist für ein System, das maximale Flexibilität zulässt, sinnvoll.  Es ist die Aufgabe von MFC, ein Standardverhalten für MFC\-\/C\+\+\-Programme zu implementieren.  
  
 Um die Implementierung von MFC von [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) zu verstehen, müssen Sie zuerst verstehen, was diese Schnittstelle ist.  Eine vereinfachte Version von [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) wird unten definiert:  
  
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
  
 Die Memberfunktionen [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) und [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) steuern die Speicherverwaltung des Objekts.  COM verwendet Verweiszählungsschema, um Objekte nachzuverfolgen.  Auf ein Objekt wird nie direkt verwiesen wie in C\+\+.  Stattdessen wird auf COM\-Objekte immer durch einen Zeiger verwiesen.  Um das Objekt freizugeben, wenn der Besitzer es nicht mehr benötigt, wird der [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317)\-Member des Objekts aufgerufen \(im Gegensatz zur Verwendung des Operators "delete" wie für ein herkömmliches C\+\+\-Objekt\).  Dank des Verweiszählmechanismus können mehrere Verweise auf ein einzelnes Objekt verwaltet werden.  Eine Implementierung von [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) und [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) verwaltet einen Verweiszähler für das Objekt – das Objekt wird erst gelöscht, wenn der entsprechende Verweiszähler 0 erreicht.  
  
 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) und [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) sind aus Sicht der Implementierung recht einfach.  Im Folgenden wird eine einfache Implementierung veranschaulicht:  
  
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
  
 Die [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)Memberfunktion ist etwas interessanter.  Ein Objekt, dessen einzige Memberfunktionen [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) und [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) sind, ist nicht besonders interessant. Das Objekt sollte Anweisungen erfüllen können, die über die von der [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)\-Schnittstelle bereitgestellten hinausgehen.  An diesem Punkt ist die [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)\-Funktion nützlich.  Sie ermöglicht Ihnen, eine andere "Schnittstelle" für dasselbe Objekt zu erhalten.  Diese Schnittstellen werden normalerweise von [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) abgeleitet und fügen weitere Funktionen hinzu, indem neuen Memberfunktionen hinzugefügt werden.  Für COM\-Schnittstellen werden nie Membervariablen in der Schnittstelle deklariert, und alle Memberfunktionen werden als rein virtuell deklariert.  Beispiel:  
  
```  
class IPrintInterface : public IUnknown  
{  
public:  
    virtual void PrintObject() = 0;  
};  
```  
  
 Um ein IPrintInterface\-Objekt abzurufen, wenn Sie nur [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) vorliegen haben, rufen Sie [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) mit der `IID` von **IPrintInterface** ab.  Eine `IID` ist eine 128\-Bit\-Zahl, die die Schnittstelle eindeutig identifiziert.  Für jede Schnittstelle gibt es eine `IID`, die entweder von Ihnen oder OLE definiert wird.  Wenn `pUnk` ein Zeiger auf ein [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)\-Objekt ist, kann der Code zum Abrufen eines IPrintInterface\-Objekts wie folgt lauten:  
  
```  
IPrintInterface* pPrint = NULL;  
if (pUnk->QueryInterface(IID_IPrintInterface,   
    (void**)&pPrint) == NOERROR)  
{  
    pPrint->PrintObject();  
    pPrint->Release();     
        // release pointer obtained via QueryInterface  
}  
```  
  
 Das erscheint recht einfach, doch wie würden Sie ein Objekt implementieren, das sowohl das IPrintInterface\-Objekt als auch die [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)\-Schnittstelle unterstützt?  In diesem Fall ist es einfach, da das IPrintInterface\-Objekt direkt von [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) abgeleitet wird. Durch Implementieren von IPrintInterface wird [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) automatisch unterstützt.  Zum Beispiel:  
  
```  
class CPrintObj : public CPrintInterface  
{  
    virtual HRESULT QueryInterface(REFIID iid, void** ppvObj);  
    virtual ULONG AddRef();  
    virtual ULONG Release();  
    virtual void PrintObject();  
};  
```  
  
 Die Implementierungen von [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) und [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) wären absolut identisch mit den oben implementierten.  **CPrintObj::QueryInterface** würde etwa folgendermaßen aussehen:  
  
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
  
 Wenn der Schnittstellenbezeichner \(IID\) erkannt wird, wird ein Zeiger auf das Objekt zurückgegeben. Andernfalls tritt ein Fehler auf.  Beachten Sie auch, dass ein erfolgreiches [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)\-Objekt ein implizites [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)\-Objekt ergibt.  Natürlich müssten Sie auch CEditObj::Print implementieren.  Das ist einfach, da das IPrintInterface\-Objekt direkt von der [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)\-Schnittstelle abgeleitet wurde.  Wenn Sie jedoch zwei unterschiedliche Schnittstellen unterstützen möchten, die beide von [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) abgeleitet werden, berücksichtigen Sie Folgendes:  
  
```  
class IEditInterface : public IUnkown  
{  
public:  
    virtual void EditObject() = 0;  
};  
```  
  
 Obwohl es mehrere Möglichkeiten gibt, eine Klasse zu implementieren, die IEditInterface und IPrintInterface unterstützt, einschließlich Verwenden der C\+\+\-Mehrfachvererbung, konzentriert sich dieser Hinweis auf die Verwendung von geschachtelten Klassen zur Implementierung dieser Funktionalität.  
  
```  
class CEditPrintObj  
{  
public:  
    CEditPrintObj();  
  
    HRESULT QueryInterface(REFIID iid, void**);  
    ULONG AddRef();  
    ULONG Release();  
    DWORD m_dwRef;  
  
    class CPrintObj : public IPrintInterface  
    {  
    public:  
        CEditPrintObj* m_pParent;  
        virtual HRESULT QueryInterface(REFIID iid, void** ppvObj);  
        virtual ULONG AddRef();  
        virtual ULONG Release();  
    } m_printObj;  
  
    class CEditObj : public IEditInterface  
    {  
    public:  
        CEditPrintObj* m_pParent;  
        virtual ULONG QueryInterface(REFIID iid, void** ppvObj);  
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
  
HRESULT CEditPrintObj::QueryInterface(REFIID iid, void** ppvObj)  
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
    REFIID iid, void** ppvObj)   
{   
    return m_pParent->QueryInterface(iid, ppvObj);   
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
    REFIID iid, void** ppvObj)   
{   
    return m_pParent->QueryInterface(iid, ppvObj);   
}  
```  
  
 Beachten Sie, dass die meisten der [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) \-Implementierungen in die CEditPrintObj\-Klasse platziert werden, statt den Code in CEditPrintObj::CEditObj und in CEditPrintObj::CPrintObj zu duplizieren.  So wird die Codemenge reduziert und Fehler vermieden.  Wichtig ist, dass es möglich ist, von der IUnknown\-Schnittstelle aus [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) aufzurufen, um eine Schnittstelle abzurufen, die vom Objekt unterstützt wird. Von jeder dieser Schnittstellen aus kann derselbe Vorgang ausgeführt werden.  Dies bedeutet, dass alle [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)\-Funktionen, die von den einzelnen Schnittstellen verfügbar sind, sich absolut identisch verhalten müssen.  Damit diese eingebetteten Objekte die Implementierung im "äußeren Objekt" aufrufen kann, wird ein Gegenzeiger verwendet \(m\_pParent\).  Der m\_pParent\-Zeiger wird während des CEditPrintObj\-Konstruktors initialisiert.  Anschließend würden Sie CEditPrintObj::CPrintObj::PrintObject und CEditPrintObj::CEditObj::EditObject ebenfalls implementieren.  Es wurde relativ viel Code für eine Funktion, die Fähigkeit zum Bearbeiten des Objekts, hinzugefügt.  Glücklicherweise ist es recht selten, dass Schnittstellen nur über eine einzelne Memberfunktion verfügen \(es kann jedoch durchaus vorkommen\) und in diesem Fall würden EditObject und PrintObject normalerweise zu einer einzelnen Schnittstelle kombiniert werden.  
  
 Das ist eine umfassende Erläuterung und viel Code für ein solch einfaches Szenario.  Die MFC\/OLE\-Klassen stellen eine einfachere Alternative zur Verfügung.  Die MFC\-Implementierung verwendet eine Technik, die mit der Methode vergleichbar ist, mit der Windows\-Meldungen mit Meldungszuordnungen umschlossen werden.  Diese Funktion wird als *Schnittstellenzuordnungen* bezeichnet und im nächsten Abschnitt erläutert.  
  
## MFC\-Schnittstellenzuordnungen  
 MFC\/OLE beinhaltet die Implementierung von "Schnittstellenzuordnungen", die in Bezug auf Konzept und in der Ausführung den "Meldungszuordnungen" und "Dispatchzuordnungen" von MFC ähneln.  Die Kernfunktionen der Schnittstellenzuordnungen von MFC sind folgende:  
  
-   Eine Standardimplementierung von [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), die in die `CCmdTarget`\-Klasse integriert ist.  
  
-   Wartung des Verweiszählers, der von [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) und [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) modifiziert wird  
  
-   Datengesteuerte Implementierung von [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)  
  
 Außerdem unterstützen Schnittstellenzuordnungen die folgenden erweiterten Funktionen:  
  
-   Unterstützung für das Erstellen von aggregatfähigen COM\-Objekten  
  
-   Unterstützung für das Verwenden von aggregierten Objekten in der Implementierung eines COM\-Objekts  
  
-   Die Implementierung ist "hookable" und erweiterbar  
  
 Weitere Informationen zum Aggregieren finden Sie im Thema [Aggregation](http://msdn.microsoft.com/library/windows/desktop/ms686558\(v=vs.85\).aspx).  
  
 Die Unterstützung der Schnittstellenzuordnung von MFC haben ihren Stammpfad in der `CCmdTarget`\-Klasse.  `CCmdTarget` "*has\-a*" Verweiszähler sowie alle Memberfunktionen, die mit der [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)\-Implementierung verknüpft werden \(der Verweiszähler ist beispielsweise in `CCmdTarget`\).  Um eine Klasse zu erstellen, die OLE\-COM unterstützt, leiten Sie eine Klasse von `CCmdTarget` ab, und verwenden Sie verschiedene Makros sowie Memberfunktionen von `CCmdTarget`, um die gewünschten Schnittstellen zu implementieren.  Die Implementierung von MFC verwendet geschachtelte Klassen, um die jeweilige Schnittstellenimplementierung ähnlich wie im Beispiel oben zu definieren.  Dies wird mit einer Standardimplementierung von IUnknown sowie mit einer Reihe von Makros erleichtert, durch die ein Teil des sich wiederholenden Codes entfällt.  
  
## Grundlagen zu Schnittstellenzuordnungen  
  
#### So implementieren Sie eine Klasse mithilfe der Schnittstellenzuordnungen von MFC  
  
1.  Leiten Sie eine Klasse entweder direkt oder indirekt von `CCmdTarget` ab.  
  
2.  Verwenden Sie die `DECLARE_INTERFACE_MAP`\-Function in der abgeleiteten Klassendefinition.  
  
3.  Verwenden Sie für jede Schnittstelle, die Sie unterstützen möchten, die Makros `BEGIN_INTERFACE_PART` und `END_INTERFACE_PART` in der Klassendefinition.  
  
4.  Verwenden Sie in der Implementierungsdatei die Makros `BEGIN_INTERFACE_MAP` und `END_INTERFACE_MAP`, um die Schnittstellenzuordnung der Klasse zu definieren.  
  
5.  Für jede unterstützte IID verwenden Sie das `INTERFACE_PART`\-Makro zwischen den Makros `BEGIN_INTERFACE_MAP` und `END_INTERFACE_MAP`, um diese IID einem bestimmten "Teil" der Klasse zuzuordnen.  
  
6.  Implementieren Sie die geschachtelten Klassen, die die von Ihnen unterstützten Schnittstellen darstellen.  
  
7.  Verwenden Sie das `METHOD_PROLOGUE`\-Makro, um auf das übergeordnete Element, das von `CCmdTarget` abgeleitete Objekt, zuzugreifen.  
  
8.  [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) und [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) können zur `CCmdTarget`\-Implementierung dieser Funktionen delegieren \(`ExternalAddRef`, `ExternalRelease` und `ExternalQueryInterface`\).  
  
 Das obige CPrintEditObj\-Beispiel kann implementiert wie folgt werden:  
  
```  
class CPrintEditObj : public CCmdTarget  
{  
public:  
    // member data and member functions for CPrintEditObj go here  
  
// Interface Maps  
protected:  
    DECLARE_INTERFACE_MAP()  
  
    BEGIN_INTERFACE_PART(EditObj, IEditInterface)  
        STDMETHOD_(void, EditObject)();  
    END_INTERFACE_PART(EditObj)  
  
    BEGIN_INTERFACE_PART(PrintObj, IPrintInterface)  
        STDMETHOD_(void, PrintObject)();  
    END_INTERFACE_PART(PrintObj)  
};  
```  
  
 Die obige Deklaration erstellt eine Klasse, die von `CCmdTarget` abgeleitet wird.  Das `DECLARE_INTERFACE_MAP`\-Makro teilt dem Framework mit, dass diese Klasse eine benutzerdefinierte Schnittstellenzuordnung hat.  Darüber hinaus definieren die Makros `BEGIN_INTERFACE_PART` und `END_INTERFACE_PART` geschachtelte Klassen, in diesem Fall mit den Namen CEditObj und CPrintObj \(das X wird nur verwendet, um die geschachtelten Klassen von globalen Klassen, die mit "C" beginnen, und von Schnittstellenklassen zu unterscheiden, die mit "I" beginnen\).  Zwei geschachtelte Member dieser Klassen werden erstellt: m\_CEditObj bzw. m\_CPrintObj.  Die Makros deklarieren automatisch die Funktionen [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) und [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521). Daher deklarieren Sie nur spezifischen Funktionen für diese Schnittstelle: EditObject und PrintObject \(das OLE Makro\- `STDMETHOD` wird verwendet, damit `_stdcall` und virtuelle Schlüsselwörter nach Bedarf für die Zielplattform bereitgestellt werden\).  
  
 So implementieren Sie Schnittstellenzuordnung für diese Klasse:  
  
```  
BEGIN_INTERFACE_MAP(CPrintEditObj, CCmdTarget)  
    INTERFACE_PART(CPrintEditObj, IID_IPrintInterface, PrintObj)  
    INTERFACE_PART(CPrintEditObj, IID_IEditInterface, EditObj)  
END_INTERFACE_MAP()  
```  
  
 Damit wird die IID "IID\_IPrintInterface" mit "m\_CPrintObj" und "IID\_IEditInterface" mit "m\_CEditObj" verbunden.  Die `CCmdTarget`\-Implementierung von [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) \(`CCmdTarget::ExternalQueryInterface`\) verwendet diese Zuordnung, um auf Anforderung Zeiger auf "m\_CPrintObj" und "m\_CEditObj" zurückzugeben.  Es ist nicht erforderlich, einen Eintrag für `IID_IUnknown` einzuschließen. Das Framework verwendet die erste Schnittstelle in der Zuordnung \(in diesem Fall "m\_CPrintObj"\), wenn `IID_IUnknown` angefordert wird.  
  
 Obwohl das `BEGIN_INTERFACE_PART`\-Makro die Funktionen [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) und [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) automatisch deklariert hat, müssen Sie sie dennoch implementieren:  
  
```  
ULONG FAR EXPORT CEditPrintObj::XEditObj::AddRef()  
{  
    METHOD_PROLOGUE(CEditPrintObj, EditObj)  
    return pThis->ExternalAddRef();  
}  
  
ULONG FAR EXPORT CEditPrintObj::XEditObj::Release()  
{  
    METHOD_PROLOGUE(CEditPrintObj, EditObj)  
    return pThis->ExternalRelease();  
}  
  
HRESULT FAR EXPORT CEditPrintObj::XEditObj::QueryInterface(  
    REFIID iid, void FAR* FAR* ppvObj)  
{  
    METHOD_PROLOGUE(CEditPrintObj, EditObj)  
    return (HRESULT)pThis->ExternalQueryInterface(&iid, ppvObj);  
}  
  
void FAR EXPORT CEditPrintObj::XEditObj::EditObject()  
{  
    METHOD_PROLOGUE(CEditPrintObj, EditObj)  
    // code to "Edit" the object, whatever that means...  
}  
```  
  
 Die Implementierung für CEditPrintObj::CPrintObj entspricht weitgehend den oben beschriebenen Definitionen für CEditPrintObj::CEditObj.  Obwohl es möglich wäre, ein Makro zu erstellen, mit dem diese Funktionen automatisch generiert werden \(was am Anfang der MFC\/OLE\-Entwicklung der Fall war\), wird es schwierig, Haltepunkte festzulegen, wenn ein Makro mehrere Codezeilen generiert.  Aus diesem Grund wird dieser Code manuell erweitert.  
  
 Durch Verwendung der Frameworkimplementierung von Meldungszuordnungen mussten einige Vorgänge nicht ausgeführt werden:  
  
-   Implementieren von QueryInterface  
  
-   Implementieren von AddRef und Release  
  
-   Deklarieren eine dieser integrierten Methoden auf beiden Schnittstellen  
  
 Darüber hinaus verwendet das Framework Meldungszuordnungen intern.  So können Sie aus einer Frameworkklasse ableiten, beispielsweise `COleServerDoc`, die bereits bestimmte Schnittstellen unterstützt und entweder Ersatz oder Hinzufügungen zu den Schnittstellen bereitstellt, die im Framework enthalten sind.  Dies ist möglich, da das Framework das Erben einer Schnittstellenzuordnung von einer Basisklasse vollständig unterstützt.  Dies ist der Grund, warum `BEGIN_INTERFACE_MAP` als zweiten Parameter den Namen der Basisklasse verwendet.  
  
> [!NOTE]
>  Es ist im Allgemeinen nicht möglich, die Implementierung der integrierten MFC\-Implementierungen der OLE\-Schnittstellen nur durch Vererben der eingebetteten Spezialisierung dieser Schnittstelle von der MFC\-Version wiederzuverwenden.  Dies ist nicht möglich, da die Verwendung des `METHOD_PROLOGUE`\-Makros für den Zugriff auf das enthaltende von `CCmdTarget` abgeleitete Objekt einen *festen Offset* eines eingebetteten Objekts des von `CCmdTarget` abgeleiteten Objekts impliziert.  Dies bedeutet z. B., dass Sie kein eingebettetes XMyAdviseSink von der MFC\-Implementierung in `COleClientItem::XAdviseSink` ableiten können, da XAdviseSink sich an einem bestimmten Offset oben im `COleClientItem`\-Objekt befinden muss.  
  
> [!NOTE]
>  Sie können alle Funktionen, für die das Standardverhalten von MFC gelten soll, jedoch an die MFC\-Implementierung delegieren.  Dies wird in der MFC\-Implementierung von `IOleInPlaceFrame` \(XOleInPlaceFrame\) in der `COleFrameHook`\-Klasse ausgeführt \(sie delegiert viele Funktionen zu m\_xOleInPlaceUIWindow\).  Dieser Entwurf wurde ausgewählt, um die Laufzeitgröße von Objekten zu reduzieren, die viele Schnittstellen implementieren. Mit diesem Entwurf ist kein Gegenzeiger mehr erforderlich \(wie bei Verwendung von m\_pParent im vorherigen Abschnitt\).  
  
### Aggregation und Schnittstellenzuordnungen  
 Zusätzlich zur Unterstützung von eigenständigen COM\-Objekten unterstützt MFC auch Aggregation.  Die Aggregation an sich ist ein zu komplexes Thema, daher kann sie hier nicht erläutert werden. Weitere Informationen über die Aggregation finden Sie im Thema [Aggregation](http://msdn.microsoft.com/library/windows/desktop/ms686558\(v=vs.85\).aspx).  Dieser Hinweis beschreibt einfach die Unterstützung für die Aggregation, die in den Framework und die Schnittstellenzuordnungen integriert ist.  
  
 Es gibt zwei Möglichkeiten, Aggregation zu verwenden: \(1\) mit einem COM\-Objekt, das Aggregation unterstützt und \(2\) durch Implementierung eines Objekts, von einem anderen aggregiert werden kann.  Diese Funktionen können als "Verwenden eines Aggregatobjekts" und "Ausstatten einer Objekt\-Implementierung mit Aggregatfähigkeit" bezeichnet werden.  MFC unterstützt beide Funktionen.  
  
### Verwenden eines Aggregatobjekts  
 Zur Verwendung eines Aggregatobjekts, muss es eine Methode geben, um das Aggregat in den QueryInterface\-Mechanismus einzubinden.  Das heißt, das Aggregatobjekt muss sich wie ein systemeigener Teil des Objekts verhalten.  Wie lässt sich dieses Objekt in den Schnittstellenzuordnungsmechanismus von MFC einbinden?  Zusätzlich zum `INTERFACE_PART`\-Makro, mit dem ein geschachteltes Objekt einer IID zugeordnet wird, können Sie ein Aggregatobjekt auch als Teil der von `CCmdTarget` abgeleiteten Klasse deklarieren.  Dazu wird das `INTERFACE_AGGREGATE`\-Makro verwendet.  Dies ermöglicht es Ihnen, eine Membervariable anzugeben \(die ein Zeiger auf eine [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) oder abgeleitete Klasse sein muss\), die in den Schnittstellenzuordnungsmechanismus integriert werden soll.  Wenn der Zeiger beim Aufrufen von `CCmdTarget::ExternalQueryInterface` nicht NULL ist, ruft das Framework automatisch die [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)\-Memberfunktion des Aggregatobjekts auf, wenn die angeforderte `IID` nicht zu den systemeigenen `IID`s gehört, die vom `CCmdTarget`\-Objekt selbst unterstützt werden.  
  
##### So verwenden Sie das INTERFACE\_AGGREGATE\-Makro  
  
1.  Deklarieren Sie eine Membervariable \(`IUnknown*`\), die einen Zeiger auf das Aggregatobjekt enthält.  
  
2.  Schließen Sie ein `INTERFACE_AGGREGATE`\-Makro in die Schnittstellenzuordnung ein, die anhand des Namens auf die Membervariable verweist.  
  
3.  Daraufhin \(normalerweise während `CCmdTarget::OnCreateAggregates`\) initialisieren Sie die Membervariable auf einen anderen Wert als NULL.  
  
 Zum Beispiel:  
  
```  
class CAggrExample : public CCmdTarget  
{  
public:  
    CAggrExample();  
  
protected:  
    LPUNKNOWN m_lpAggrInner;  
    virtual BOOL OnCreateAggregates();  
  
    DECLARE_INTERFACE_MAP()  
    // "native" interface part macros may be used here  
};  
  
CAggrExample::CAggrExample()  
{  
    m_lpAggrInner = NULL;  
}  
  
BOOL CAggrExample::OnCreateAggregates()  
{  
    // wire up aggregate with correct controlling unknown  
    m_lpAggrInner = CoCreateInstance(CLSID_Example,  
        GetControllingUnknown(), CLSCTX_INPROC_SERVER,  
        IID_IUnknown, (LPVOID*)&m_lpAggrInner);  
    if (m_lpAggrInner == NULL)  
        return FALSE;  
    // optionally, create other aggregate objects here  
    return TRUE;  
}  
  
BEGIN_INTERFACE_MAP(CAggrExample, CCmdTarget)  
    // native "INTERFACE_PART" entries go here  
    INTERFACE_AGGREGATE(CAggrExample, m_lpAggrInner)  
END_INTERFACE_MAP()  
```  
  
 Die m\_lpAggrInner\-Variable wird im Konstruktor auf NULL initialisiert.  Das Framework ignoriert eine Membervariable mit dem Wert NULL in der Standardimplementierung von [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521).  Das `OnCreateAggregates`\-Objekt eignet sich gut, um die Aggregatobjekte tatsächlich zu erstellen.  Sie müssen dieses Objekt explizit aufrufen, wenn Sie das Objekt außerhalb der MFC\-Implementierung von `COleObjectFactory` erstellen.  Der Grund für das Erstellen von Aggregaten in `CCmdTarget::OnCreateAggregates` und die Verwendung von `CCmdTarget::GetControllingUnknown` wird offensichtlich, wenn das Erstellen von aggregatfähigen Objekten erläutert wird.  
  
 Mit dieser Methode erhält das Objekt alle Schnittstellen, die das Aggregatobjekt unterstützt, sowie deren systemeigene Schnittstellen.  Wenn Sie nur eine Teilmenge der Schnittstellen benötigen, die das Aggregat unterstützt, können Sie `CCmdTarget::GetInterfaceHook` überschreiben.  Dies ermöglicht eine "Hookability" auf niedriger Ebene, ähnlich wie bei [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521).  Normalerweise werden alle Schnittstellen gewünscht, die das Aggregat unterstützt.  
  
### Ausstatten einer Objekt\-Implementierung mit Aggregationsfähigkeit  
 Damit ein Objekt aggregationsfähig ist, muss die Implementierung von [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) und [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) an ein "controlling unknown"\-Objekt delegiert werden. Das bedeutet, dass es, um Teil des Objekts zu werden, [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) und [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) an ein anderes Objekt delegieren muss, das auch von [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) abgeleitet ist.  Dieses "controlling unknown"\-Objekt wird dem Objekt beim Erstellen zur Verfügung gestellt, d. h., es wird der Implementierung von `COleObjectFactory` bereitgestellt.  Das Implementieren bedeutet einen geringen Mehraufwand, und in einigen Fällen ist es nicht wünschenswert, sodass dies laut MFC optional ist.  Um ein Objekt aggregatfähig zu machen, rufen Sie `CCmdTarget::EnableAggregation` im Konstruktor des Objekts auf.  
  
 Wenn das Objekt auch Aggregate verwendet, müssen Sie zudem sicherstellen, das richtige "controlling unknown"\-Objekt an die Aggregatobjekte zu übergeben.  Normalerweise wird dieser [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)\-Zeiger an das Objekt übergeben, wenn das Aggregat erstellt wird.  Beispielsweise ist der pUnkOuter\-Parameter der "controlling unknown"\-Zeiger für Objekte, die mit `CoCreateInstance` erstellt werden.  Der richtige "controlling unknown"\-Zeiger kann durch Aufrufen von `CCmdTarget::GetControllingUnknown` abgerufen werden.  Der Wert, der von dieser Funktion zurückgegeben wird, ist jedoch während des Konstruktors ungültig.  Aus diesem Grund wird vorgeschlagen, die Aggregate nur in einer Überschreibung von `CCmdTarget::OnCreateAggregates` zu erstellen, bei der der Rückgabewert von `GetControllingUnknown` zuverlässig ist, auch wenn er von der `COleObjectFactory`\-Implementierung erstellt wird.  
  
 Wichtig ist auch, dass das Objekt den richtigen Verweiszähler bearbeitet, wenn künstliche Verweiszähler hinzugefügt oder freigegeben werden.  Um dies sicherzustellen, rufen Sie immer `ExternalAddRef` und `ExternalRelease` statt `InternalRelease` und `InternalAddRef` auf.  Es passiert nur selten, dass `InternalRelease` oder `InternalAddRef` für eine Klasse aufgerufen werden, die Aggregation unterstützt.  
  
### Referenzmaterial  
 Die erweiterte Verwendung von OLE, wie Definieren eigener Schnittstellen oder Überschreiben der Implementierung des Frameworks der OLE\-Schnittstellen, erfordert die Nutzung des zugrunde liegenden Schnittstellenzuordnungsmechanismus.  
  
 In diesem Abschnitt werden alle Makros und APIs erläutert, die zum Implementieren dieser erweiterten Funktionen verwendet werden.  
  
### CCmdTarget::EnableAggregation – Funktionsbeschreibung  
  
```  
  
void EnableAggregation();  
```  
  
## Hinweise  
 Rufen Sie diese Funktion im Konstruktor der abgeleiteten Klasse auf, wenn Sie OLE\-Aggregation für Objekte dieses Typs unterstützen möchten.  Dadurch wird eine besondere IUnknown\-Implementierung vorbereitet, die für aggregatfähige Objekte erforderlich ist.  
  
### CCmdTarget::ExternalQueryInterface – Funktionsbeschreibung  
  
```  
  
              DWORD ExternalQueryInterface(    const void FAR* lpIID,    LPVOID FAR* ppvObj   
);  
```  
  
## Hinweise  
  
#### Parameter  
 `lpIID`  
 Ein ferner Zeiger auf eine IID \(das erste Argument für QueryInterface\)  
  
 `ppvObj`  
 Ein Zeiger auf ein IUnknown\*\-Objekt \(das zweite Argument für QueryInterface\)  
  
## Hinweise  
 Rufen Sie diese Funktion in der Implementierung von IUnknown für jede Schnittstelle auf, die Ihre Klasse implementiert.  Diese Funktion stellt die datengesteuerte Standardimplementierung von QueryInterface auf Grundlage der Schnittstellenzuordnung des Objekts bereit.  Es ist erforderlich, den Rückgabewert in ein HRESULT umzuwandeln.  Wenn das Objekt aggregiert wird, ruft diese Funktion das "controlling IUnknown"\-Objekt auf, anstatt die lokale Schnittstellenzuordnung zu verwenden.  
  
### CCmdTarget::ExternalAddRef – Funktionsbeschreibung  
  
```  
  
DWORD ExternalAddRef();  
```  
  
## Hinweise  
 Rufen Sie diese Funktion in der Implementierung von IUnknown::AddRef für jede Schnittstelle auf, die Ihre Klasse implementiert.  Der Rückgabewert ist der neue Verweiszähler für das CCmdTarget\-Objekt.  Wenn das Objekt aggregiert wird, ruft diese Funktion das "controlling IUnknown"\-Objekt auf, anstatt den lokalen Verweiszähler zu bearbeiten.  
  
### CCmdTarget::ExternalRelease – Funktionsbeschreibung  
  
```  
  
DWORD ExternalRelease();  
  
```  
  
## Hinweise  
 Rufen Sie diese Funktion in der Implementierung von IUnknown::Release für jede Schnittstelle auf, die Ihre Klasse implementiert.  Der Rückgabewert gibt den neuen Verweiszähler für das Objekt an.  Wenn das Objekt aggregiert wird, ruft diese Funktion das "controlling IUnknown"\-Objekt auf, anstatt den lokalen Verweiszähler zu bearbeiten.  
  
### DECLARE\_INTERFACE\_MAP – Makrobeschreibung  
  
```  
  
DECLARE_INTERFACE_MAP  
  
```  
  
## Hinweise  
 Verwenden Sie dieses Makro in einer Klasse, die von `CCmdTarget` abgeleitet ist und über eine Schnittstellenzuordnung verfügt.  Dieses Makro wird auf die gleiche Weise wie `DECLARE_MESSAGE_MAP` verwendet.  Dieser Makroaufruf sollte in die Klassendefinition, normalerweise in einer Headerdatei \(.H\), platziert werden.  Eine Klasse mit `DECLARE_INTERFACE_MAP` muss die Schnittstellenzuordnung in der Implementierungsdatei \(.CPP\) mit den Makros `BEGIN_INTERFACE_MAP` und `END_INTERFACE_MAP` definieren.  
  
### BEGIN\_INTERFACE\_PART und END\_INTERFACE\_PART – Makrobeschreibungen  
  
```  
  
              BEGIN_INTERFACE_PART(   
   localClass,  
   iface   
);  
END_INTERFACE_PART(   
   localClass   
)  
```  
  
## Hinweise  
  
#### Parameter  
 l`ocalClass`  
 Der Name der Klasse, die die Schnittstelle implementiert  
  
 `iface`  
 Der Name der Schnittstelle, die diese Klasse implementiert  
  
## Hinweise  
 Für jede Schnittstelle, die die Klasse implementiert, müssen Sie ein aus `BEGIN_INTERFACE_PART` und `END_INTERFACE_PART` bestehendes Paar besitzen.  Diese Makros definieren eine lokale Klasse, die von der von Ihnen definierten OLE\-Schnittstelle abgeleitet wird, sowie eine eingebettete Membervariable dieser Klasse.  Die Member [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) und [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) werden automatisch deklariert.  Sie müssen die Deklarationen für die anderen Memberfunktionen einschließen, die ein Teil der Schnittstelle sind, die implementiert wurde \(diese Deklarationen werden zwischen die Makros `BEGIN_INTERFACE_PART` und `END_INTERFACE_PART` platziert\).  
  
 Das `iface`\-Argument ist die OLE\-Schnittstelle, die Sie implementieren möchten\), wie `IAdviseSink` oder `IPersistStorage` \(oder eine eigene benutzerdefinierte Schnittstelle\).  
  
 Das `localClass`\-Argument ist der Name der lokalen Klasse, die definiert wird.  Der Buchstabe "x" wird dem Namen automatisch vorangestellt.  Diese Namenskonvention wird verwendet, um Konflikte mit gleichnamigen globalen Klassen zu vermeiden.  Außerdem der Name des eingebetteten Members, der dem `localClass`\-Namen entspricht, außer dass "m\_x" vorangestellt wird.  
  
 Zum Beispiel:  
  
```  
BEGIN_INTERFACE_PART(MyAdviseSink, IAdviseSink)  
   STDMETHOD_(void,OnDataChange)(LPFORMATETC, LPSTGMEDIUM);  
   STDMETHOD_(void,OnViewChange)(DWORD, LONG);  
   STDMETHOD_(void,OnRename)(LPMONIKER);  
   STDMETHOD_(void,OnSave)();  
   STDMETHOD_(void,OnClose)();  
END_INTERFACE_PART(MyAdviseSink)  
```  
  
 würde eine lokale Klasse mit dem Namen XMyAdviseSink definieren, der von IAdviseSink abgeleitet wurde, und ein Member der Klasse, in der es als m\_xMyAdviseSink.Note deklariert wird:  
  
> [!NOTE]
>  Die Zeilen, die mit `STDMETHOD`\_ beginnen, werden im Wesentlichen aus OLE2.H kopiert und geringfügig geändert.  Durch Kopieren aus OLE2.H lassen sich Fehler reduzieren, die andernfalls schwer zu beheben sind.  
  
### BEGIN\_INTERFACE\_MAP und END\_INTERFACE\_MAP – Makrobeschreibungen  
  
```  
  
              BEGIN_INTERFACE_MAP(   
   theClass,  
   baseClass   
) END_INTERFACE_MAP  
```  
  
## Hinweise  
  
#### Parameter  
 `theClass`  
 Die Klasse, in der die Schnittstellenzuordnung definiert werden soll  
  
 `baseClass`  
 Die Klasse, von der `theClass` abgeleitet wird.  
  
## Hinweise  
 Die Makros `BEGIN_INTERFACE_MAP` und `END_INTERFACE_MAP` werden in der Implementierungsdatei verwendet, um die Schnittstellenzuordnung tatsächlich zu definieren.  Für jede Schnittstelle, die implementiert wird, gibt es eine oder mehrere `INTERFACE_PART`\-Makroaufrufe.  Für jedes Aggregat, das diese Klasse verwendet, gibt es einen `INTERFACE_AGGREGATE`\-Makroaufruf.  
  
### INTERFACE\_PART – Makrobeschreibung  
  
```  
  
              INTERFACE_PART(   
   theClass,  
   iid,   
   localClass   
)  
```  
  
## Hinweise  
  
#### Parameter  
 `theClass`  
 Der Name der Klasse, die die Schnittstellenzuordnung enthält.  
  
 `iid`  
 Die `IID`, die der eingebetteten Klasse zugeordnet werden soll.  
  
 `localClass`  
 Der Name der lokalen Klasse \(ohne das "X"\).  
  
## Hinweise  
 Dieses Makro wird zwischen dem `BEGIN_INTERFACE_MAP`\-Makro und dem `END_INTERFACE_MAP`\-Makro für jede Schnittstelle verwendet, die von dem Objekt unterstützt wird.  So können Sie eine IID zu einem Member der Klasse zuordnen, die von `theClass` und `localClass` angegeben ist.  Das "m\_x" wird `localClass` automatisch hinzugefügt.  Beachten Sie, dass maximal eine `IID` mit einem einzigen Member zugeordnet werden kann.  Dies ist hilfreich, wenn Sie nur eine "am stärksten abgeleitete" Schnittstelle implementieren und alle Zwischenschnittstellen ebenfalls bereitstellen möchten.  Ein gutes Beispiel hierfür ist die `IOleInPlaceFrameWindow`\-Schnittstelle.  Die Hierarchie sieht wie folgt aus:  
  
```  
IUnknown  
    IOleWindow  
        IOleUIWindow  
            IOleInPlaceFrameWindow  
```  
  
 Wenn ein Objekt `IOleInPlaceFrameWindow` implementiert, kann ein Client `QueryInterface` auf den folgenden Schnittstellen aufrufen: `IOleUIWindow`, `IOleWindow` oder [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), neben der "am stärksten abgeleiteten" Schnittstelle `IOleInPlaceFrameWindow` \(die Schnittstelle, die Sie wirklich implementieren\).  Um Abhilfe zu schaffen, können Sie mehrere `INTERFACE_PART`\-Makros verwenden, um der `IOleInPlaceFrameWindow`\-Schnittstelle jede mögliche Basisschnittstelle zuzuordnen:  
  
 in der Klassendefinitionsdatei:  
  
```  
BEGIN_INTERFACE_PART(CMyFrameWindow, IOleInPlaceFrameWindow)  
```  
  
 in der Klassenimplementierungsdatei:  
  
```  
BEGIN_INTERFACE_MAP(CMyWnd, CFrameWnd)  
    INTERFACE_PART(CMyWnd, IID_IOleWindow, MyFrameWindow)  
    INTERFACE_PART(CMyWnd, IID_IOleUIWindow, MyFrameWindow)  
    INTERFACE_PART(CMyWnd, IID_IOleInPlaceFrameWindow, MyFrameWindow)  
END_INTERFACE_MAP  
```  
  
 Das Framework berücksichtigt IUnknown, da es immer erforderlich ist.  
  
### INTERFACE\_PART – Makrobeschreibung  
  
```  
  
              INTERFACE_AGGREGATE(   
   theClass,  
   theAggr   
)  
```  
  
## Hinweise  
  
#### Parameter  
 `theClass`  
 Der Name der Klasse, die die Schnittstellenzuordnung enthält,  
  
 `theAggr`  
 Der Name der Membervariable, die aggregiert werden soll.  
  
## Hinweise  
 Dieses Makro wird verwendet, um dem Framework mitzuteilen, dass die Klasse ein Aggregatobjekt verwendet.  Es muss zwischen den Makros `BEGIN_INTERFACE_PART` und `END_INTERFACE_PART` erscheinen.  Ein Aggregatobjekt ist ein separates Objekt, das von [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) abgeleitet ist.  Indem Sie ein Aggregat und das `INTERFACE_AGGREGATE`\-Makro verwenden, können Sie alle Schnittstellen, die vom Aggregat unterstützt werden, erscheinen lassen, als würden sie vom Objekt direkt unterstützt werden.  Das `theAggr`\-Argument ist einfach der Name einer Membervariable der Klasse, die von [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) abgeleitet ist \(entweder direkt oder indirekt\).  Alle `INTERFACE_AGGREGATE`\-Makros müssen den `INTERFACE_PART`\-Makros folgen, wenn sie in eine Schnittstellenzuordnung eingefügt werden.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)