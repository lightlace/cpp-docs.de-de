---
title: 'TN039: MFC-OLE-Automatisierungsimplementierung'
ms.date: 06/28/2018
f1_keywords:
- vc.mfc.ole
helpviewer_keywords:
- MFC, COM support
- IDispatch interface
- MFC, OLE DB and
- TN039
- Automation, MFC COM interface entry points
ms.assetid: 765fa3e9-dd54-4f08-9ad2-26e0546ff8b6
ms.openlocfilehash: cd6f8d681ef7e6517f2172ca6b22b13723a962fd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62305488"
---
# <a name="tn039-mfcole-automation-implementation"></a>TN039: MFC/OLE-Automatisierungsimplementierung

> [!NOTE]
> Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

## <a name="overview-of-ole-idispatch-interface"></a>Übersicht über die OLE-IDispatch-Schnittstelle

Die `IDispatch` Schnittstelle ist die Möglichkeit, die mit dem Anwendungen verfügbar zu machen, Methoden und Eigenschaften, die andere Anwendungen wie z. B. Visual BASIC oder andere Sprachen können z. B. von Features der Anwendung verwenden. Der wichtigste Teil dieser Schnittstelle ist die `IDispatch::Invoke` Funktion. MFC verwendet "Dispatchzuordnungen" implementieren `IDispatch::Invoke`. Die Dispatchzuordnung erläutert, die MFC-Implementierung des Layouts oder "Form" Ihre `CCmdTarget`-Klassen abgeleitet, sodass es direkt bearbeiten die Eigenschaften des Objekts kann, oder rufen Sie die Memberfunktionen in das Objekt zu erfüllen `IDispatch::Invoke` Anforderungen.

Zum größten Teil, ermöglichen ClassWizard und MFC die meisten Details der OLE-Automatisierung aus den Anwendungsprogrammierer ausblenden. Der Programmierer konzentriert sich auf die eigentliche Funktionalität, in der Anwendung verfügbar zu machen und verfügt nicht über die zugrunde liegende Infrastruktur kümmern.

Es gibt Fälle, allerdings es erforderlich ist, um zu verstehen, was hinter den Kulissen MFC macht. In diesem Hinweis geht es um das Framework wie weist **DISPID**s, um der Member-Funktionen und Eigenschaften. Kenntnisse des-Algorithmus MFC zum Zuweisen von verwendet **DISPID**s ist nur erforderlich, wenn Sie wissen müssen, die IDs, z. B. bei der Erstellung einer "Typbibliothek" für Ihre Anwendung Objekte.

## <a name="mfc-dispid-assignment"></a>MFC DISPID Zuweisung

Obwohl die Endbenutzer der Automatisierung (Benutzer von Visual Basic, z. B.), sieht die tatsächlichen Namen der aktiviert der Automatisierungs, Eigenschaften und Methoden in ihrem Code (z. B. obj. ShowWindow), die Implementierung der `IDispatch::Invoke` empfängt nicht die tatsächlichen Namen. Aus Gründen der Optimierung, die er empfängt eine **DISPID**, das ist eine 32-Bit-"Magic Cookie", die beschreibt, die Methode oder Eigenschaft, die auf die zugegriffen werden. Diese **DISPID** werden Werte zurückgegeben, aus der `IDispatch` Implementierung durch eine andere Methode namens `IDispatch::GetIDsOfNames`. Ruft eine Automatisierungsclientanwendung `GetIDsOfNames` nach für jeden Member oder die Eigenschaft zugreifen darf, und für spätere Aufrufe zwischenspeichern soll `IDispatch::Invoke`. Auf diese Weise die teure Zeichenfolgensuche erfolgt nur einmal pro Objekt verwenden, anstatt einmal pro `IDispatch::Invoke` aufrufen.

MFC bestimmt die **DISPID**für jede Methode und Eigenschaft basierend auf zwei Dinge:

- Der Abstand zwischen dem oberen Rand der Dispatchzuordnung (1, relativ)

- Der Abstand der Dispatchzuordnung in der abgeleitetsten Klasse (relative 0)

Die **DISPID** ist in zwei Teile unterteilt. Die **LOWORD** von der **DISPID** enthält die erste Komponente, die den Abstand zwischen dem oberen Rand der Dispatchzuordnung. Die **HIWORD** enthält die Entfernung von der am stärksten abgeleitete Klasse. Zum Beispiel:

```cpp
class CDispPoint : public CCmdTarget
{
public:
    short m_x, m_y;
    // ...
    DECLARE_DISPATCH_MAP()
    // ...
};

class CDisp3DPoint : public CDispPoint
{
public:
    short m_z;
    // ...
    DECLARE_DISPATCH_MAP()
    // ...
};

BEGIN_DISPATCH_MAP(CDispPoint, CCmdTarget)
    DISP_PROPERTY(CDispPoint, "x", m_x, VT_I2)
    DISP_PROPERTY(CDispPoint, "y", m_y, VT_I2)
END_DISPATCH_MAP()

BEGIN_DISPATCH_MAP(CDisp3DPoint, CDispPoint)
    DISP_PROPERTY(CDisp3DPoint, "z", m_z, VT_I2)
END_DISPATCH_MAP()
```

Wie Sie sehen können, gibt es zwei Klassen, die beide Schnittstellen für OLE-Automatisierung verfügbar zu machen. Einer dieser Klassen, die von der anderen abgeleitet ist und daher nutzt die Funktionen von der Basisklasse, einschließlich des Teils der OLE-Automatisierung ("X" und "y" Eigenschaften in diesem Fall).

MFC generiert **DISPID**s für die-Klasse CDispPoint wie folgt:

```cpp
property X    (DISPID)0x00000001
property Y    (DISPID)0x00000002
```

Da die Eigenschaften nicht in einer Basisklasse, sind die **HIWORD** von der **DISPID** ist immer 0 (null) (die Entfernung von der am stärksten abgeleitete Klasse für CDispPoint ist 0 (null)).

MFC generiert **DISPID**s für die-Klasse CDisp3DPoint wie folgt:

```cpp
property Z    (DISPID)0x00000001
property X    (DISPID)0x00010001
property Y    (DISPID)0x00010002
```

Die Z-Eigenschaft erhält eine **DISPID** mit einer NULL **HIWORD** , da sie in der Klasse definiert ist, die die Eigenschaften, CDisp3DPoint verfügbar gemacht wird. Da die X- und Y-Eigenschaften in einer Basisklasse definiert sind die **HIWORD** von der **DISPID** 1 ist, da die Klasse, die in der folgenden Eigenschaften definiert sind in einem Abstand von einer Ableitung die am stärksten abgeleitete Klasse ist.

> [!NOTE]
> Die **LOWORD** wird immer durch die Position in der Zuordnung bestimmt auch, wenn Einträge in der Zuordnung mit expliziten vorhanden sind **DISPID** (Informationen finden Sie weiter Abschnitt auf den **_ID** Versionen der `DISP_PROPERTY` und `DISP_FUNCTION` Makros).

## <a name="advanced-mfc-dispatch-map-features"></a>Erweiterte MFC-Dispatch-Map-Features

Es gibt zahlreiche weitere Funktionen, die Klassen-Assistenten nicht unterstützt. mit dieser Version von Visual C++. Klassen-Assistent unterstützt `DISP_FUNCTION`, `DISP_PROPERTY`, und `DISP_PROPERTY_EX` die eine Methode, Variable Elementeigenschaft und get-/Set-Funktionseigenschaft bzw. definieren. Diese Funktionen sind in der Regel alles, die was benötigt wird, um die meisten Automatisierungsserver zu erstellen.

Die folgenden zusätzlichen Makros können verwendet werden, wenn die Makros, die Klassen-Assistent unterstützt nicht angemessen sind: `DISP_PROPERTY_NOTIFY`, und `DISP_PROPERTY_PARAM`.

## <a name="disppropertynotify--macro-description"></a>DISP_PROPERTY_NOTIFY – Makrobeschreibung

```cpp
DISP_PROPERTY_NOTIFY(
    theClass,
    pszName,
    memberName,
    pfnAfterSet,
    vtPropType)
```

### <a name="parameters"></a>Parameter

*theClass*<br/>
Der Name der Klasse.

*pszName*<br/>
Externer Name der Eigenschaft.

*memberName*<br/>
Der Name der Membervariablen, die in der die Eigenschaft gespeichert wird.

*pfnAfterSet*<br/>
Name des Member-Funktion aufrufen, wenn die Eigenschaft geändert wird.

*vtPropType*<br/>
Ein Wert, der den Typ der Eigenschaft angibt.

### <a name="remarks"></a>Hinweise

Dieses Makro entspricht weitgehend DISP_PROPERTY, außer dass es sich um ein zusätzliches Argument akzeptiert. Das zusätzliche Argument *PfnAfterSet,* muss eine Memberfunktion, die keinen Wert zurückgibt und nimmt keine Parameter, "" void "OnPropertyNotify()". Wird aufgerufen **nach** die Membervariable geändert wurde.

## <a name="disppropertyparam--macro-description"></a>DISP_PROPERTY_PARAM – Makrobeschreibung

```cpp
DISP_PROPERTY_PARAM(
    theClass,
    pszName,
    pfnGet,
    pfnSet,
    vtPropType,
    vtsParams)
```

### <a name="parameters"></a>Parameter

*theClass*<br/>
Der Name der Klasse.

*pszName*<br/>
Externer Name der Eigenschaft.

*memberGet*<br/>
Der Name der Memberfunktion verwendet, um die Eigenschaft abzurufen.

*memberSet*<br/>
Der Name der Memberfunktion verwendet, um die Eigenschaft festzulegen.

*vtPropType*<br/>
Ein Wert, der den Typ der Eigenschaft angibt.

*vtsParams*<br/>
Eine Zeichenfolge mit Leerzeichen getrennte VTS_ für jeden Parameter.

### <a name="remarks"></a>Hinweise

Wie die DISP_PROPERTY_EX-Makro definiert dieses Makro viel eine Eigenschaft, die mit separaten Get- und Set-Member-Funktionen zugegriffen. Dieses Makro, Ihnen jedoch zu eine Parameterliste für die Eigenschaft angeben. Dies ist nützlich für die Eigenschaften, die indiziert oder parametrisiert werden auf andere Weise implementieren. Die Parameter werden immer zuerst platziert gefolgt von den neuen Wert für die Eigenschaft. Zum Beispiel:

```cpp
DISP_PROPERTY_PARAM(CMyObject, "item", GetItem, SetItem, VT_DISPATCH, VTS_I2 VTS_I2)
```

würde entsprechen, zum Abrufen und Festlegen der Member-Funktionen:

```cpp
LPDISPATCH CMyObject::GetItem(short row, short col)
void CMyObject::SetItem(short row, short col, LPDISPATCH newValue)
```

## <a name="dispxxxxid--macro-descriptions"></a>DISP_XXXX_ID – Makrobeschreibungen

```cpp
DISP_FUNCTION_ID(
    theClass,
    pszName,
    dispid,
    pfnMember,
    vtRetVal,
    vtsParams)
DISP_PROPERTY_ID(
    theClass,
    pszName,
    dispid,
    memberName,
    vtPropType)
DISP_PROPERTY_NOTIFY_ID(
    theClass,
    pszName,
    dispid,
    memberName,
    pfnAfterSet,
    vtPropType)
DISP_PROPERTY_EX_ID(
    theClass,
    pszName,
    dispid,
    pfnGet,
    pfnSet,
    vtPropType)
DISP_PROPERTY_PARAM_ID(
    theClass,
    pszName,
    dispid,
    pfnGet,
    pfnSet,
    vtPropType,
    vtsParams)
```

### <a name="parameters"></a>Parameter

*theClass*<br/>
Der Name der Klasse.

*pszName*<br/>
Externer Name der Eigenschaft.

*dispid*<br/>
Die festen DISPID für die Eigenschaft oder Methode.

*pfnGet*<br/>
Der Name der Memberfunktion verwendet, um die Eigenschaft abzurufen.

*pfnSet*<br/>
Der Name der Memberfunktion verwendet, um die Eigenschaft festzulegen.

*memberName*<br/>
Der Name der Membervariable der Eigenschaft zugeordnet.

*vtPropType*<br/>
Ein Wert, der den Typ der Eigenschaft angibt.

*vtsParams*<br/>
Eine Zeichenfolge mit Leerzeichen getrennte VTS_ für jeden Parameter.

### <a name="remarks"></a>Hinweise

Diese Makros können Sie eine **DISPID** eines anstatt MFC automatisch zuweisen. Diese erweiterten Makros die gleichen Namen verfügen, außer dass es sich bei dieser ID auf den Makronamen angefügt wird (z. B. **DISP_PROPERTY_ID**), und die ID wird bestimmt durch den Parameter angegebene direkt nach der *PszName* Parameter. Finden Sie unter AFXDISP. Für Weitere Informationen zu diesen Makros H. Die **_ID** Einträge am Ende der Dispatchzuordnung platziert werden müssen. Sie wirkt sich auf die automatische **DISPID** Generation in die gleiche Weise wie einen nicht-**_ID** Version des Makros würde (der **DISPID**s werden anhand der Position bestimmt). Zum Beispiel:

```cpp
BEGIN_DISPATCH_MAP(CDisp3DPoint, CCmdTarget)
    DISP_PROPERTY(CDisp3DPoint, "y", m_y, VT_I2)
    DISP_PROPERTY(CDisp3DPoint, "z", m_z, VT_I2)
    DISP_PROPERTY_ID(CDisp3DPoint, "x", 0x00020003, m_x, VT_I2)
END_DISPATCH_MAP()
```

MFC DISPIDs für CDisp3DPoint-Klasse wie folgt generiert:

```cpp
property X    (DISPID)0x00020003
property Y    (DISPID)0x00000002
property Z    (DISPID)0x00000001
```

Angeben einer festen **DISPID** ist nützlich, um Abwärtskompatibilität zu einer bereits vorhandenen Verteilschnittstelle oder bestimmte System definierten Methoden oder Eigenschaften zu implementieren (angegeben in der Regel um einen negativen Wert  **DISPID**, z. B. die **DISPID_NEWENUM** Auflistung).

## <a name="retrieving-the-idispatch-interface-for-a-coleclientitem"></a>Abrufen der IDispatch-Schnittstelle für eine COleClientItem

Viele Server unterstützt die Automatisierung in ihrer Dokumentobjekte, zusammen mit der OLE-Server-Funktionalität. Um den Zugriff auf dieses Automation-Schnittstelle ist es erforderlich, direkt den Zugriff der `COleClientItem::m_lpObject` Membervariablen gespeichert. Der folgende Code Ruft die `IDispatch` -Schnittstelle für ein Objekt abgeleitet `COleClientItem`. Sie können den folgenden Code in der Anwendung einschließen, wenn Sie diese Funktion erforderlichen finden:

```cpp
LPDISPATCH CMyClientItem::GetIDispatch()
{
    ASSERT_VALID(this);
    ASSERT(m_lpObject != NULL);

    LPUNKNOWN lpUnk = m_lpObject;

    Run();      // must be running

    LPOLELINK lpOleLink = NULL;
    if (m_lpObject->QueryInterface(IID_IOleLink,
        (LPVOID FAR*)&lpOleLink) == NOERROR)
    {
        ASSERT(lpOleLink != NULL);
        lpUnk = NULL;
        if (lpOleLink->GetBoundSource(&lpUnk) != NOERROR)
        {
            TRACE0("Warning: Link is not connected!\n");
            lpOleLink->Release();
            return NULL;
        }
        ASSERT(lpUnk != NULL);
    }

    LPDISPATCH lpDispatch = NULL;
    if (lpUnk->QueryInterface(IID_IDispatch, &lpDispatch) != NOERROR)
    {
        TRACE0("Warning: does not support IDispatch!\n");
        return NULL;
    }

    ASSERT(lpDispatch != NULL);
    return lpDispatch;
}
```

Die Dispatchschnittstelle zurückgegeben wird, über diese Funktion kann dann direkt verwendet oder angefügt eine `COleDispatchDriver` für Typsicherer Zugriff. Wenn Sie es direkt verwenden, stellen Sie sicher, dass Sie Aufrufen der `Release` Member beim über mit dem Mauszeiger (die `COleDispatchDriver` Destruktor ist dies standardmäßig).

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
