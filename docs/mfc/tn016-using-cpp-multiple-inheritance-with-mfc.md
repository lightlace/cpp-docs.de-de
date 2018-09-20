---
title: 'TN016: Verwenden von C++-Mehrfachvererbung mit MFC | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.inheritance
dev_langs:
- C++
helpviewer_keywords:
- TN016
- MI (Multiple Inheritance)
- multiple inheritance, MFC support for
ms.assetid: 4ee27ae1-1410-43a5-b111-b6af9b84535d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c0ed5c1bc73f58bec1f9ad0d6a790fe3d3c0239
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444683"
---
# <a name="tn016-using-c-multiple-inheritance-with-mfc"></a>TN016: Verwenden von C++-Mehrfachvererbung mit MFC

Dieser Hinweis beschreibt, wie mehrfache Vererbung (MI) mit der Microsoft Foundation Classes. Die Verwendung von MI muss nicht mit MFC. MI, nicht in alle MFC_Klassen verwendet und ist nicht erforderlich, eine Klassenbibliothek schreiben.

In den folgenden Unterthemen wird beschrieben, wie MI für die Verwendung von allgemeinen MFC-Ausdrücke sowie deckt einige der Einschränkungen der MI auswirkt. Einige dieser Einschränkungen sind allgemeine Einschränkungen für C++. Andere werden von der MFC-Architektur auferlegt.

Am Ende dieser technischen Hinweis finden Sie eine vollständige MFC-Anwendung, die MI verwendet.

## <a name="cruntimeclass"></a>CRuntimeClass

Die Persistenz- und ein dynamisches Objekt Erstellungsverfahren von MFC nutzen die [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) Datenstruktur zur eindeutigen Identifizierung von Klassen. MFC ordnet eine dieser Strukturen jede dynamische und/oder serialisierbare Klasse in Ihrer Anwendung. Diese Strukturen werden initialisiert, wenn die Anwendung startet mit einer speziellen statische Objekt vom Typ `AFX_CLASSINIT`.

Die aktuelle Implementierung von `CRuntimeClass` MI-Laufzeit-Typinformationen nicht unterstützt. Dies bedeutet nicht, dass Sie MI in der MFC-Anwendung verwenden können. Allerdings müssen Sie bestimmte Verantwortlichkeiten, bei der Arbeit mit Objekten, die mehr als einer Basisklasse haben.

Die [CObject:: IsKindOf](../mfc/reference/cobject-class.md#iskindof) Methode wird nicht ordnungsgemäß ermittelt den Typ eines Objekts, wenn es mehrere Basisklassen verfügt. Aus diesem Grund können keine [CObject](../mfc/reference/cobject-class.md) als virtuelle Basisklasse aus, und alle Aufrufe von `CObject` Memberfunktionen wie [CObject:: Serialize](../mfc/reference/cobject-class.md#serialize) und [CObject::operator neue](../mfc/reference/cobject-class.md#operator_new)Bereich Qualifizierer muss haben werden, damit diese C++ den entsprechende Funktionsaufruf eindeutig machen können. Wenn ein Programm MI in MFC verwendet, die Klasse, enthält die `CObject` Basisklasse muss die Klasse am weitesten links in der Liste der Basisklassen sein.

Eine Alternative ist die Verwendung der `dynamic_cast` Operator. Umwandlung eines Objekts mit MI auf einen der zugehörigen Basisklassen erzwingt, dass den Compiler die Funktionen in der angegebenen Basisklasse verwendet wird. Weitere Informationen finden Sie unter [Dynamic_cast-Operator](../cpp/dynamic-cast-operator.md).

## <a name="cobject---the-root-of-all-classes"></a>CObject - Stamm aller Klassen

Alle wichtige Klassen abgeleitet werden direkt oder indirekt von Klasse `CObject`. `CObject` enthält keine Daten, aber verfügt über einige Standardfunktionen. Wenn Sie auf "MI" verwenden, Sie in der Regel erbt von mindestens zwei `CObject`-abgeleiteten Klassen. Im folgende Beispiel wird veranschaulicht, wie eine Klasse erben kann eine [CFrameWnd](../mfc/reference/cframewnd-class.md) und [CObList](../mfc/reference/coblist-class.md):

```cpp
class CListWnd : public CFrameWnd, public CObList
{
    // ...
};
CListWnd myListWnd;
```

In diesem Fall `CObject` zweimal enthalten ist. Dies bedeutet, dass Sie eine Möglichkeit, alle Verweise auf eindeutig `CObject` Methoden oder Operatoren. Die **new-Operator** und [Delete-Operator](../mfc/reference/cobject-class.md#operator_delete) sind zwei Operatoren, die eindeutig gemacht werden müssen. Wenn Sie beispielsweise verursacht der folgende Code einen Fehler zur Kompilierzeit:

```cpp
myListWnd.Dump(afxDump); // compile time error, CFrameWnd::Dump or CObList::Dump
```

## <a name="reimplementing-cobject-methods"></a>Neuimplementieren CObject-Methoden

Wenn Sie eine neue Klasse erstellen verfügt über zwei oder mehr `CObject` Basisklassen abgeleitete sollten Sie erneut die `CObject` Methoden, die andere Benutzer verwenden sollen. Operatoren **neue** und **löschen** sind obligatorisch und [Dump](../mfc/reference/cobject-class.md#dump) wird empfohlen. Das folgende Beispiel Reimplements der **neue** und **löschen** Operatoren und die `Dump` Methode:

```cpp
class CListWnd : public CFrameWnd, public CObList
{
public:
    void* operator new(size_t nSize)
    {
        return CFrameWnd:: operator new(nSize);
    }
    void operator delete(void* p)
    {
        CFrameWnd:: operator delete(p);
    }
    void Dump(CDumpContent& dc)
    {
        CFrameWnd::Dump(dc);
        CObList::Dump(dc);
    }
    // ...
};
```

## <a name="virtual-inheritance-of-cobject"></a>Virtuelle Vererbung von CObject

Es mag so scheinen, praktisch erben `CObject` würde das Problem der Mehrdeutigkeit der Funktion, aber das ist nicht der Fall. Da es keine Memberdaten in `CObject`, nicht virtuellen Vererbung, um zu verhindern, dass mehrere Kopien der Daten eine Basisklasse erforderlich. Im ersten Beispiel, das zuvor gezeigt wurde die `Dump` virtuelle Methode ist immer noch mehrdeutig, da es anders in implementiert wird `CFrameWnd` und `CObList`. Die beste Möglichkeit, um Mehrdeutigkeit ist, befolgen Sie die Empfehlungen, die im vorherigen Abschnitt angezeigt.

## <a name="cobjectiskindof-and-run-time-typing"></a>CObject:: IsKindOf und Laufzeit-Eingabe

Der Mechanismus der Laufzeit eingeben von MFC in unterstützt `CObject` werden die Makros DECLARE_DYNAMIC, IMPLEMENT_DYNAMIC, DECLARE_DYNCREATE, IMPLEMENT_DYNCREATE, DECLARE_SERIAL und IMPLEMENT_SERIAL. Diese Makros können eine Laufzeit-Typinformationen Prüfung sicher Typumwandlungen garantieren ausführen.

Diese Makros unterstützt nur eine einzige Basisklasse und funktioniert auf eingeschränkte Weise für multiply geerbten Klassen. Die Basisklasse, die Sie in IMPLEMENT_DYNAMIC oder IMPLEMENT_SERIAL angeben, muss die erste (oder ganz links)-Basisklasse. Bei dieser Platzierung können Sie überprüfen, die für die am weitesten links Basisklasse nur eingeben. Die Runtime-Typsystem werden keine Informationen über weitere Basisklassen bemerken. Im folgenden Beispiel erfolgt die Run-Time-Systeme typüberprüfung für `CFrameWnd`, aber nichts über wissen `CObList`.

```cpp
class CListWnd : public CFrameWnd, public CObList
{
    DECLARE_DYNAMIC(CListWnd)
    // ...
};
IMPLEMENT_DYNAMIC(CListWnd, CFrameWnd)
```

## <a name="cwnd-and-message-maps"></a>CWnd und Meldungszuordnungen

Es gibt zwei zusätzliche Anforderungen, für das MFC-Nachrichtensystem Zuordnung ordnungsgemäß funktioniert:

- Es muss nur eine `CWnd`-Basisklasse abgeleitet.

- Die `CWnd`-abgeleiteten Basisklasse muss die erste (oder ganz links) Basisklasse sein.

Hier sind einige Beispiele, die nicht verwendet werden:

```cpp
class CTwoWindows : public CFrameWnd, public CEdit
{ /* ... */ }; // error : two copies of CWnd

class CListEdit : public CObList, public CEdit
{ /* ... */ }; // error : CEdit (derived from CWnd) must be first
```

## <a name="a-sample-program-using-mi"></a>Ein Beispielprogramm MI

Im folgende Beispiel ist eine eigenständige Anwendung, die aus einer abgeleiteten Klasse besteht `CFrameWnd` und [CWinApp](../mfc/reference/cwinapp-class.md). Wir empfehlen nicht, dass Sie eine Anwendung auf diese Weise strukturieren, aber dies ist ein Beispiel der kleinste MFC-Anwendung, die eine Klasse.

```cpp
#include <afxwin.h>

class CHelloAppAndFrame : public CFrameWnd, public CWinApp
{
public:
    CHelloAppAndFrame() {}

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

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
