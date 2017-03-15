---
title: "TN016: Verwenden von C++-Mehrfachvererbung mit MFC"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.inheritance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MI (Mehrfachvererbung)"
  - "Mehrfachvererbung, MFC-Unterstützung für"
  - "TN016"
ms.assetid: 4ee27ae1-1410-43a5-b111-b6af9b84535d
caps.latest.revision: 22
caps.handback.revision: "18"
ms.author: "mblome"
manager: "ghogen"
---
# TN016: Verwenden von C++-Mehrfachvererbung mit MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Hinweis wird beschrieben, wie mehrfache Vererbung \(MI\) mit Microsoft Foundation Classes verwendet.  Die Verwendung von MI wird nicht mit MFC benötigt.  MI wird in keine MFC\-Klassen verwendet und ist nicht erforderlich, eine Klassenbibliothek.  
  
 In den folgenden Abschnitten wird beschrieben, wie MI die Verwendung allgemeiner MFC\-Idiomen beeinflusst sowie einige Beschränkungen der MI abdeckt.  Einige dieser Beschränkungen sind Einschränkungen allgemeinen C\+\+.  Andere werden durch die MFC\-Architektur erzwingt.  
  
 Am Ende dieses technischen Hinweises finden Sie eine vollständige MFC\-Anwendung, die MI verwendet.  
  
## CRuntimeClass  
 Die Erstellungsmechanismen der Beibehaltung und dynamischer Objekte von MFC verwendet die [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) Datenstruktur, um Klassen eindeutig identifizieren.  MFC ordnet einer dieser Strukturen mit jeder dynamischen und\/oder serialisierbaren Klasse in der Anwendung an.  Diese Strukturen werden beim Start der Anwendung initialisiert, indem ein spezielles statisches Objekt vom Typ `AFX_CLASSINIT` verwendet.  
  
 Die aktuelle Implementierung von `CRuntimeClass` unterstützt nicht MI\-Laufzeittypinformationen.  Dies bedeutet nicht, dass Sie MI in der MFC\-Anwendung nicht verwenden können.  Sie haben jedoch bestimmten Verantwortlichkeiten, wenn Sie mit Objekten arbeiten, die mehr als eine Basisklasse haben.  
  
 Die Methode [CObject::IsKindOf](../Topic/CObject::IsKindOf.md) nicht ordnungsgemäß bestimmt den Typ eines Objekts, wenn diese mehrere Basisklassen hat.  Daher können Sie die [CObject](../mfc/reference/cobject-class.md) nicht als virtuelle Basisklasse verwenden, und alle Aufrufe `CObject`\-Memberfunktionen wie [CObject::Serialize](../Topic/CObject::Serialize.md) und [CObject::operator new](../Topic/CObject::operator%20new.md) müssen Bereichsqualifizierer haben, sodass C\+\+ den entsprechenden Funktionsaufruf unterscheiden kann.  Wenn ein Programm MI in MFC verwendet, muss die Klasse, die die `CObject` \- Basisklasse enthält, die am weitesten links liegende Klasse in der Liste der Basisklassen sein.  
  
 Eine Alternative ist `dynamic_cast`, den Operator zu verwenden.  Ein Objekt mit MI bis eine ihrer Basisklassen Downcasting, erzwingt der Compiler, um die in der angegebenen Basisklasse verwenden.  Weitere Informationen finden Sie unter [dynamic\_cast\-Operator](../cpp/dynamic-cast-operator.md).  
  
## CObject \- Stamm aller Klassen  
 Alle signifikanten Klassen ableiten direkt oder indirekt von der Klasse `CObject`.  `CObject` hat keine Memberdaten, verfügt jedoch über einige Standardfunktionalität.  Wenn Sie MI verwenden, erben Sie in der Regel von zwei oder mehr `CObject` abgeleitete Klassen.  Das folgende Beispiel veranschaulicht, wie eine Klasse von [CFrameWnd](../mfc/reference/cframewnd-class.md) und [CObList](../mfc/reference/coblist-class.md) erben kann:  
  
```  
class CListWnd : public CFrameWnd, public CObList  
{  
 ...  
};  
CListWnd myListWnd;  
```  
  
 In diesem Fall wird `CObject` zweimal enthalten.  Dies bedeutet, dass Sie eine Methode erforderlich, jeden Verweis auf `CObject`\-Methoden oder Operatoren zu unterscheiden.  `operator new` und [Operator](../Topic/CObject::operator%20delete.md) sind zwei Operatoren, die eindeutig bestimmt werden müssen.  Ein weiteres Beispiel verursacht der folgende Code einen Fehler zur Kompilierzeit:  
  
```  
myListWnd.Dump(afxDump);  
    // compile time error, CFrameWnd::Dump or CObList::Dump ?  
```  
  
## Erneute Implementieren von CObject\-Methoden  
 Wenn Sie eine neue Klasse erstellen, die zwei oder mehr `CObject` ableite Basisklassen, sollten Sie die Methoden `CObject` erneut implementieren, dass Sie andere Personen verwenden soll.  Operatoren `new` und `delete` sind erforderlich und [Dumps](../Topic/CObject::Dump.md) wird empfohlen.  Das nächste Beispiel implementiert die Operatoren `new` und `delete` und die `Dump`\-Methode erneut:  
  
```  
class CListWnd : public CFrameWnd, public CObList  
{  
public:  
    void* operator new(size_t nSize)  
        { return CFrameWnd::operator new(nSize); }  
    void operator delete(void* p)  
        { CFrameWnd::operator delete(p); }  
  
    void Dump(CDumpContent& dc)  
        { CFrameWnd::Dump(dc);  
          CObList::Dump(dc); }  
     ...  
};  
```  
  
## Virtuelle Vererbung von CObject  
 Es wird, dass `CObject` virtuell erben das Problem der Funktionsmehrdeutigkeit lösen kann, jedoch ist dies nicht der Fall.  Da keine Memberdaten in `CObject` gibt, benötigen Sie keine virtuelle Vererbung, mehrere Kopien Basisklassenmemberdaten zu verhindern.  Im ersten Beispiel, das früher angezeigt wurde, ist die virtuelle Methode `Dump` noch mehrdeutig, da anders in `CFrameWnd` und `CObList` implementiert wird.  Die beste Möglichkeit, um Zweideutigkeit zu entfernen ist, den Empfehlungen zu folgen, die im vorherigen Abschnitt erstellt werden.  
  
## CObject::IsKindOf und Ablauftypisierung  
 Der Ablauftypisierungsmechanismus, der von MFC in `CObject` unterstützt wird, verwendet die Makros `DECLARE_DYNAMIC`, `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE`, `IMPLEMENT_DYNCREATE`, `DECLARE_SERIAL` und `IMPLEMENT_SERIAL`.  Diese Makros können eine Ablauftypüberprüfung ausführen, um sichere Umwandlungen sicherzustellen.  
  
 Diese Makros unterstützen nur eine einzige Basisklasse und werden in einer eingeschränkten Weise multiplizieren für geerbte Klassen arbeiten.  Die Basisklasse, die in `IMPLEMENT_DYNAMIC` oder `IMPLEMENT_SERIAL` angeben, muss die erste \(oder ganz links\) Basisklasse sein.  Platzierung Diese ermöglicht es Ihnen, Typüberprüfung für nur die am weitesten links stehende Basisklasse verwenden.  Das Ablauftypsystem weiß nichts über zusätzliche Basisklassen.  Im folgenden Beispiel ist die Ablaufsysteme Typüberprüfung für `CFrameWnd`, jedoch nichts über `CObList` wissen.  
  
```  
class CListWnd : public CFrameWnd, public CObList  
{  
    DECLARE_DYNAMIC(CListWnd)  
    ...  
};  
IMPLEMENT_DYNAMIC(CListWnd, CFrameWnd)  
```  
  
## CWnd Meldungszuordnungen und  
 Damit das MFC\-Meldungszuordnungssystem ordnungsgemäß funktioniert, werden zwei weitere Anforderungen:  
  
-   Es darf nur ein `CWnd` geben abgeleitete Basisklasse.  
  
-   `CWnd` abgeleitete Basisklasse muss die erste \(oder ganz links\) Basisklasse sein.  
  
 Hier einige Beispiele, die nicht funktionieren:  
  
```  
class CTwoWindows : public CFrameWnd, public CEdit  
    { ... };  
        // error : two copies of CWnd  
  
class CListEdit : public CObList, public CEdit  
    { ... };  
        // error : CEdit (derived from CWnd) must be first  
```  
  
## Ein mit MIs Beispielprogramm  
 Im folgenden Beispiel ist eine eigenständige Anwendung, die aus einer Klasse besteht, die von `CFrameWnd` und [CWinApp](../mfc/reference/cwinapp-class.md) abgeleitet wird.  Es empfiehlt sich nicht, dass Sie eine Anwendung auf diese Weise strukturieren, aber dies ist ein Beispiel der kleinsten MFC\-Anwendung, die eine Klasse.  
  
```  
#include <afxwin.h>  
  
class CHelloAppAndFrame : public CFrameWnd, public CWinApp  
{   
public:  
    CHelloAppAndFrame()  
        { }  
  
    // Necessary because of MI disambiguity  
    void* operator new(size_t nSize)  
        { return CFrameWnd::operator new(nSize); }  
    void operator delete(void* p)  
        { CFrameWnd::operator delete(p); }  
  
    // Implementation  
    // CWinApp overrides  
    virtual BOOL InitInstance();  
    // CFrameWnd overrides  
    virtual void PostNcDestroy();  
    afx_msg void OnPaint();  
  
    DECLARE_MESSAGE_MAP()  
  
};  
  
BEGIN_MESSAGE_MAP(CHelloAppAndFrame, CFrameWnd)  
    ON_WM_PAINT()  
END_MESSAGE_MAP()  
  
// because the frame window is not allocated on the heap, we must  
// override PostNCDestroy not to delete the frame object  
void CHelloAppAndFrame::PostNcDestroy()  
{  
    // do nothing (do not call base class)  
}  
  
void CHelloAppAndFrame::OnPaint()  
{  
    CPaintDC dc(this);  
    CRect rect;  
    GetClientRect(rect);  
  
    CString s = "Hello, Windows!";  
    dc.SetTextAlign(TA_BASELINE | TA_CENTER);  
    dc.SetTextColor(::GetSysColor(COLOR_WINDOWTEXT));  
    dc.SetBkMode(TRANSPARENT);  
    dc.TextOut(rect.right / 2, rect.bottom / 2, s);  
}  
  
// Application initialization  
BOOL CHelloAppAndFrame::InitInstance()  
{  
    // first create the main frame  
    if (!CFrameWnd::Create(NULL, "Multiple Inheritance Sample",  
        WS_OVERLAPPEDWINDOW, rectDefault))  
        return FALSE;  
  
    // the application object is also a frame window  
    m_pMainWnd = this;            
    ShowWindow(m_nCmdShow);  
    return TRUE;  
}  
  
CHelloAppAndFrame theHelloAppAndFrame;  
```  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)