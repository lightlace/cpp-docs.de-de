---
title: 'TN016: Verwenden von C++-Mehrfachvererbung mit MFC | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.inheritance
dev_langs:
- C++
helpviewer_keywords:
- TN016
- MI (Multiple Inheritance)
- multiple inheritance, MFC support for
ms.assetid: 4ee27ae1-1410-43a5-b111-b6af9b84535d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b276e316ffc8ce04577532ac3b15400ee28f9f33
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tn016-using-c-multiple-inheritance-with-mfc"></a>TN016: Verwenden von C++-Mehrfachvererbung mit MFC
Dieser Hinweis wird beschrieben, wie mehrfache Vererbung (MI) mit der Microsoft Foundation Classes verwendet wird. Die Verwendung von MI ist nicht mit MFC erforderlich. MI wird von MFC-Klassen nicht verwendet und ist nicht erforderlich, die eine Klassenbibliothek schreiben.  
  
 In den folgenden Unterthemen wird beschrieben, wie MI die Verwendung der allgemeinen MFC Idiome sowie einige der Einschränkungen von MI behandelt auswirkt. Einige diese Einschränkungen sind allgemeine Einschränkungen für C++. Andere von MFC-befehlsarchitektur auferlegt werden.  
  
 Am Ende dieser technischen Hinweis finden Sie eine vollständige MFC_Anwendung, die MI verwendet.  
  
## <a name="cruntimeclass"></a>CRuntimeClass  
 Persistenz und dynamisches Objekt Erstellungsverfahren von MFC verwenden die [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) Datenstruktur zur eindeutigen Identifizierung von Klassen. MFC ordnet diese Struktur jede dynamische und/oder serialisierbare Klasse in der Anwendung. Diese Strukturen werden initialisiert, beim Starten der Anwendung mithilfe eines speziellen statische Objekts vom Typ `AFX_CLASSINIT`.  
  
 Die aktuelle Implementierung von `CRuntimeClass` MI Laufzeit-Typinformationen nicht unterstützt. Dies bedeutet nicht, dass Sie MI in der MFC-Anwendung verwenden können. Allerdings müssen Sie bestimmte Aufgaben beim Arbeiten mit Objekten, die mehr als einer Basisklasse haben.  
  
 Die [CObject:: IsKindOf](../mfc/reference/cobject-class.md#iskindof) Methode wird nicht ordnungsgemäß ermittelt den Typ eines Objekts, wenn sie mehrere Basisklassen verfügt. Aus diesem Grund können keine [CObject](../mfc/reference/cobject-class.md) als virtuelle Basisklasse und alle Aufrufe an `CObject` -Elementfunktionen wie z. B. [Einfügeoperatoren](../mfc/reference/cobject-class.md#serialize) und [CObject::operator neue](../mfc/reference/cobject-class.md#operator_new)benötigen Bereich Qualifizierer aus, damit diese C++ den entsprechende Funktionsaufruf eindeutig machen können. Wenn ein Programm MI in MFC verwendet, enthält die Klasse, die die `CObject` Basisklasse der Klasse am weitesten links in der Liste der Basisklassen sein muss.  
  
 Eine Alternative ist die Verwendung der `dynamic_cast` Operator. Umwandlung eines Objekts mit MI auf eine der zugehörigen Basisklassen zwingt den Compiler an, die Funktionen in die angegebene Basisklasse verwenden. Weitere Informationen finden Sie unter [Dynamic_cast Operator](../cpp/dynamic-cast-operator.md).  
  
## <a name="cobject---the-root-of-all-classes"></a>CObject - Stamm aller Klassen  
 Alle signifikante Klassen ableiten direkt oder indirekt von Klasse `CObject`. `CObject`ist keine Sie beliebige Memberdaten, aber sie verfügt über einige Standardfunktionen. Bei Verwendung von MI Sie in der Regel erbt von mindestens zwei `CObject`-abgeleitete Klassen. Im folgende Beispiel wird veranschaulicht, wie eine Klasse erben kann eine [CFrameWnd](../mfc/reference/cframewnd-class.md) und ein [CObList](../mfc/reference/coblist-class.md):  
  
```  
class CListWnd : public CFrameWnd, public CObList  
{  
 ...  
};  
CListWnd myListWnd;  
```  
  
 In diesem Fall `CObject` zweimal enthalten ist. Dies bedeutet, dass Sie eine Möglichkeit, alle Verweise auf eindeutig `CObject` Methoden oder Operatoren. Die `operator new` und [Delete-Operator](../mfc/reference/cobject-class.md#operator_delete) sind zwei Operatoren, die eindeutig gemacht werden müssen. Wenn Sie beispielsweise verursacht der folgende Code einen Fehler zur Kompilierzeit:  
  
```  
myListWnd.Dump(afxDump);
*// compile time error, CFrameWnd::Dump or CObList::Dump   
```  
  
## <a name="reimplementing-cobject-methods"></a>Implementierung von CObject-Methoden  
 Wenn Sie eine neue Klasse erstellt hat, zwei oder mehr `CObject` Basisklassen abgeleitet Sie implementieren sollten die `CObject` Methoden, die andere Personen verwendet werden soll. Operatoren `new` und `delete` sind obligatorisch und [Dump](../mfc/reference/cobject-class.md#dump) wird empfohlen. Das folgende Beispiel Reimplements der `new` und `delete` Operatoren und die `Dump` Methode:  
  
```  
class CListWnd : public CFrameWnd, public CObList  
{  
public:  
    void* operator new(size_t nSize)  
 { return CFrameWnd:: operator new(nSize);

}  
    void operator delete(void* p)  
 { CFrameWnd:: operator delete(p);

}  
 
    void Dump(CDumpContent& dc)  
 { CFrameWnd::Dump(dc);

    CObList::Dump(dc);

} 
 ...  
};  
```  
  
## <a name="virtual-inheritance-of-cobject"></a>Virtuelle Vererbung von CObject  
 Es scheint, praktisch erben `CObject` würde Lösung des Problems Funktion Mehrdeutigkeit, aber dies ist nicht der Fall. Da es keine Elementdaten in ist `CObject`, ist es nicht erforderlich, dass die virtuellen Vererbung, um zu verhindern, dass mehrere Kopien von einer Basisklasse Elementdaten. Im ersten Beispiel, das zuvor gezeigt wurde die `Dump` virtuelle Methode ist immer noch mehrdeutig, da sie unterschiedlich in implementiert ist `CFrameWnd` und `CObList`. Die beste Möglichkeit, um Mehrdeutigkeit ist die Empfehlungen angezeigt, die im vorherigen Abschnitt folgen.  
  
## <a name="cobjectiskindof-and-run-time-typing"></a>CObject:: IsKindOf und zur Laufzeit eingeben  
 Die Eingabe zur Laufzeit-Mechanismus von in MFC unterstützt `CObject` verwendet die Makros `DECLARE_DYNAMIC`, `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE`, `IMPLEMENT_DYNCREATE`, `DECLARE_SERIAL` und `IMPLEMENT_SERIAL`. Diese Makros können eine Überprüfung Laufzeittyp, um sichere Umwandlungen zu gewährleisten.  
  
 Diese Makros unterstützen nur eine einzelne Basisklasse und funktioniert auf eingeschränkte Weise für multiply der geerbten Klassen. Die Basisklasse, die Sie, in angeben `IMPLEMENT_DYNAMIC` oder `IMPLEMENT_SERIAL` sollte die erste (oder ganz links) Basisklasse sein. Diese Platzierung aktivieren Sie für die am weitesten links Basisklasse nur typüberprüfung. Die Laufzeit-Typsystem kennen keinerlei wissen über zusätzliche Basisklassen. Im folgenden Beispiel werden die Systeme zur Laufzeit führen typüberprüfung für `CFrameWnd`, doch kennen nichts `CObList`.  
  
```  
class CListWnd : public CFrameWnd,
    public CObList  
{  
    DECLARE_DYNAMIC(CListWnd) 
 ...  
};  
IMPLEMENT_DYNAMIC(CListWnd,
    CFrameWnd)  
```  
  
## <a name="cwnd-and-message-maps"></a>CWnd und den Meldungszuordnungen  
 Es gibt zwei zusätzliche Anforderungen, für MFC-Karte Nachrichtensystems ordnungsgemäß funktioniert:  
  
-   Es muss nicht nur einen `CWnd`-Basisklasse abgeleitet.  
  
-   Die `CWnd`-abgeleiteten Basisklasse muss die erste (oder ganz links) Basisklasse sein.  
  
 Hier sind einige Beispiele, die nicht verwendet werden:  
  
```  
class CTwoWindows : public CFrameWnd,
    public CEdit  
 { ... }; *// error : two copies of CWnd  
 
class CListEdit : public CObList,
    public CEdit  
 { ... }; *// error : CEdit (derived from CWnd) must be first  
```  
  
## <a name="a-sample-program-using-mi"></a>Ein mit MI Beispielprogramm  
 Im folgende Beispiel ist eine eigenständige Anwendung, die von einer abgeleiteten Klasse besteht aus `CFrameWnd` und [CWinApp](../mfc/reference/cwinapp-class.md). Wir empfehlen nicht, dass Sie eine Anwendung auf diese Weise strukturieren, aber dies ist ein Beispiel für die kleinste MFC-Anwendung, die eine Klasse ist.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

