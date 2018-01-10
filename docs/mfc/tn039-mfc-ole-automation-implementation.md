---
title: 'TN039: MFC-OLE-Automatisierungsimplementierung | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.ole
dev_langs: C++
helpviewer_keywords:
- MFC, COM support
- IDispatch interface
- MFC, OLE DB and
- TN039
- Automation, MFC COM interface entry points
ms.assetid: 765fa3e9-dd54-4f08-9ad2-26e0546ff8b6
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 18a5962c9b9254233b0990f19cdc1ff4f562d9cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tn039-mfcole-automation-implementation"></a>TN039: MFC/OLE-Automatisierungsimplementierung
> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
## <a name="overview-of-ole-idispatch-interface"></a>Übersicht über die OLE-IDispatch-Schnittstelle  
 Die `IDispatch` Schnittstelle dient dazu, mit dem Anwendungen verfügbar zu machen, Methoden und Eigenschaften, die andere Anwendungen, z. B. Visual BASIC oder andere Sprachen können z. B. von Features der Anwendung verwenden. Der wichtigste Teil dieser Schnittstelle ist die **IDispatch:: Invoke** Funktion. MFC verwendet "Dispatchzuordnungen" implementiert **IDispatch:: Invoke**. Die Dispatchzuordnung enthält die MFC-Implementierung-Informationen zum Layout oder "Form" Ihre `CCmdTarget`-Klassen abgeleitet, sodass es direkt bearbeiten die Eigenschaften des Objekts kann, oder rufen Sie Member Funktionen innerhalb des Objekts nicht erfüllen  **IDispatch:: Invoke** Anforderungen.  
  
 Meistens, ermöglichen ClassWizard und MFC die meisten Details der OLE-Automatisierung aus der Anwendungsprogrammierer ausblenden. Der Programmierer konzentriert sich auf die eigentlichen Funktionen in der Anwendung verfügbar gemacht und verfügt nicht über die Aufgaben, die zugrunde liegenden Gedanken.  
  
 Es gibt Fälle, allerdings es erforderlich ist, um zu verstehen, was MFC im Hintergrund ausführt. Dieser Hinweis geht es um wie das Framework weist **DISPID**s auf Member-Funktionen und Eigenschaften. Kenntnisse des-Algorithmus MFC zum Zuweisen von verwendet **DISPID**s ist nur erforderlich, wenn Sie für Ihre Anwendung Objekte die IDs, z. B. beim Erstellen einer "Typbibliothek" kennen müssen.  
  
## <a name="mfc-dispid-assignment"></a>MFC DISPID Zuweisung  
 Obwohl die Endbenutzer Automatisierung (ein Visual Basic-Benutzer, z. B.), sieht die tatsächlichen Namen des aktiviert der Automatisierungs, Eigenschaften und Methoden in ihren Code (z. B. Objekt ShowWindow), die Implementierung von **IDispatch:: Invoke** empfängt nicht die tatsächlichen Namen. Aus Gründen der Optimierung, die er empfängt eine **DISPID**, dies ist eine 32-Bit "magische Cookie", die beschreibt, die Methode oder Eigenschaft, die erfolgen muss. Diese **DISPID** Werte zurückgegeben werden, aus der `IDispatch` Implementierung durch eine andere Methode, mit dem Namen **GetIDsOfNames**. Eine Automatisierungsclientanwendung angerufen `GetIDsOfNames` nach für jeden Member oder die Eigenschaft soll den Zugriff und das Zwischenspeichern für spätere Aufrufe an **IDispatch:: Invoke**. Auf diese Weise die aufwändige Zeichenfolgensuche erfolgt nur einmal pro Objekt verwenden, anstatt einmal pro **IDispatch:: Invoke** aufrufen.  
  
 MFC bestimmt die **DISPID**s für jede Methode und Eigenschaft basierend auf zwei Dinge:  
  
-   Der Abstand vom oberen Rand der Dispatchzuordnung (1, relativ)  
  
-   Der Abstand der Dispatchzuordnung aus der am stärksten abgeleitete Klasse (relative 0)  
  
 Die **DISPID** ist in zwei Teile unterteilt. Die **LOWORD** von der **DISPID** enthält die erste Komponente, die den Abstand vom oberen Rand der Dispatchzuordnung. Die **HIWORD** den Abstand zwischen den am stärksten abgeleitete Klasse enthält. Zum Beispiel:  
  
```  
class CDispPoint : public CCmdTarget  
{  
public:  
    short m_x,
    m_y;  
 ...  
    DECLARE_DISPATCH_MAP() 
 ...  
};  
 
class CDisp3DPoint : public CDispPoint  
{  
public:  
    short m_z;  
 ...  
    DECLARE_DISPATCH_MAP() 
 ...  
};  
 
BEGIN_DISPATCH_MAP(CDispPoint,
    CCmdTarget)  
    DISP_PROPERTY(CDispPoint, "x",
    m_x,
    VT_I2)  
    DISP_PROPERTY(CDispPoint, "y",
    m_y,
    VT_I2)  
END_DISPATCH_MAP()  
 
BEGIN_DISPATCH_MAP(CDisp3DPoint,
    CDispPoint)  
    DISP_PROPERTY(CDisp3DPoint, "z",
    m_z,
    VT_I2)  
END_DISPATCH_MAP()  
```  
  
 Wie Sie sehen können, sind zwei Klassen, die OLE-Automatisierungsschnittstellen verfügbar machen. Einer dieser Klassen, die von der anderen abgeleitet ist und daher nutzt die Basisklasse-Funktionen, einschließlich des Teils der OLE-Automatisierung ("X" und "y" die Eigenschaften in diesem Fall).  
  
 MFC generiert **DISPID**s-CDispPoint wie folgt:  
  
```  
property X    (DISPID)0x00000001  
property Y    (DISPID)0x00000002  
```  
  
 Da die Eigenschaften nicht in einer Basisklasse sind die **HIWORD** von der **DISPID** ist immer 0 (null) (die Entfernung von der am stärksten abgeleitete Klasse für CDispPoint ist 0 (null)).  
  
 MFC generiert **DISPID**s-CDisp3DPoint wie folgt:  
  
```  
property Z    (DISPID)0x00000001  
property X    (DISPID)0x00010001  
property Y    (DISPID)0x00010002  
```  
  
 Die Z-Eigenschaft erhält eine **DISPID** mit einer NULL **HIWORD** , da sie in der Klasse definiert ist, die die Eigenschaften, CDisp3DPoint verfügbar macht, ist. Da die X- und Y-Eigenschaften in einer Basisklasse definiert sind die **HIWORD** von der **DISPID** beträgt 1, da die Klasse, die in der diese Eigenschaften definiert werden in einem Abstand von eine Ableitung der am stärksten abgeleitete Klasse ist.  
  
> [!NOTE]
>  Die **LOWORD** immer richtet sich nach der Position in der Zuordnung selbst, wenn vorhanden Einträge in der Zuordnung mit expliziten sind **DISPID** (finden Sie Informationen im folgenden Abschnitt auf der **_ID** Versionen der `DISP_PROPERTY` und `DISP_FUNCTION` Makros).  
  
## <a name="advanced-mfc-dispatch-map-features"></a>Erweiterte MFC-Dispatch-Kartenfunktionen  
 Es gibt diverse weitere Funktionen, die von ClassWizard nicht unterstützt in dieser Version von Visual C++. Klassen-Assistent unterstützt `DISP_FUNCTION`, `DISP_PROPERTY`, und `DISP_PROPERTY_EX` die eine Methode, die Variable Elementeigenschaft und die Elementeigenschaft Funktion Get/Set bzw. definieren. Diese Funktionen sind in der Regel alle, die benötigt wird, um die meisten Automatisierungsserver zu erstellen.  
  
 Die folgenden zusätzlichen Makros können verwendet werden, wenn die Klassen-Assistent unterstützt Makros nicht angemessen sind: `DISP_PROPERTY_NOTIFY`, und `DISP_PROPERTY_PARAM`.  
  
## <a name="disppropertynotify--macro-description"></a>DISP_PROPERTY_NOTIFY – Makrobeschreibung  
  
```  
 
    DISP_PROPERTY_NOTIFY(
 theClass,   
    pszName, 
    memberName, 
    pfnAfterSet, 
    vtPropType) 
```  
  
## <a name="remarks"></a>Hinweise  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Der Name der Klasse.  
  
 `pszName`  
 Externer Name der Eigenschaft.  
  
 `memberName`  
 Name der Membervariable, in der die Eigenschaft gespeichert ist.  
  
 `pfnAfterSet`  
 Name der Memberfunktion aufgerufen wird, wenn die Eigenschaft geändert wird.  
  
 `vtPropType`  
 Ein Wert, der den Typ der Eigenschaft.  
  
## <a name="remarks"></a>Hinweise  
 Dieses Makro ähnelt in vielerlei Hinsicht `DISP_PROPERTY`, außer dass sie ein zusätzliches Argument akzeptiert. Das zusätzliche Argument *PfnAfterSet,* sollte eine Memberfunktion, die keinen Wert zurückgibt und nimmt keine Parameter, "" void "OnPropertyNotify()" sein. Aufgerufen wird **nach** die Membervariable geändert wurde.  
  
## <a name="disppropertyparam--macro-description"></a>DISP_PROPERTY_PARAM – Makrobeschreibung  
  
```  
 
    DISP_PROPERTY_PARAM(
 theClass,   
    pszName, 
    pfnGet, 
    pfnSet, 
    vtPropType, 
    vtsParams) 
```  
  
## <a name="remarks"></a>Hinweise  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Der Name der Klasse.  
  
 `pszName`  
 Externer Name der Eigenschaft.  
  
 `memberGet`  
 Name der Elementfunktion, die zum Abrufen der Eigenschaft verwendet.  
  
 `memberSet`  
 Name der Elementfunktion verwendet, um die Eigenschaft festzulegen.  
  
 `vtPropType`  
 Ein Wert, der den Typ der Eigenschaft.  
  
 `vtsParams`  
 Eine Zeichenfolge mit Leerzeichen getrennt VTS_ für jeden Parameter.  
  
## <a name="remarks"></a>Hinweise  
 Ähnlich wie die `DISP_PROPERTY_EX` Makro dieses Makro definiert eine Eigenschaft, die mit separaten Get- und Set-Memberfunktionen zugegriffen. Dieses Makro können jedoch eine Parameterliste für die Eigenschaft an. Dies ist hilfreich bei der Implementierung von Eigenschaften, die indiziert oder parametrisiert werden auf andere Weise. Die Parameter werden immer zuerst platziert gefolgt von den neuen Wert für die Eigenschaft. Zum Beispiel:  
  
```  
DISP_PROPERTY_PARAM(CMyObject, "item",
    GetItem,
    SetItem,
    VT_DISPATCH,
    VTS_I2 VTS_I2)  
```  
  
 wird zum Abrufen und Festlegen von Memberfunktionen entsprechen:  
  
```  
LPDISPATCH CMyObject::GetItem(short row,
    short col)  
void CMyObject::SetItem(short row,
    short col,
    LPDISPATCH newValue)  
```  
  
## <a name="dispxxxxid--macro-descriptions"></a>DISP_XXXX_ID – Makrobeschreibungen  
  
```  
 
    DISP_FUNCTION_ID(
 theClass,   
    pszName, 
    dispid, 
    pfnMember, 
    vtRetVal, 
    vtsParams)DISP_PROPERTY_ID(
 theClass,   
    pszName, 
    dispid, 
    memberName, 
    vtPropType)DISP_PROPERTY_NOTIFY_ID(
 theClass,   
    pszName, 
    dispid, 
    memberName, 
    pfnAfterSet, 
    vtPropType)DISP_PROPERTY_EX_ID(
 theClass,   
    pszName, 
    dispid, 
    pfnGet, 
    pfnSet, 
    vtPropType)DISP_PROPERTY_PARAM_ID(
 theClass,   
    pszName, 
    dispid, 
    pfnGet, 
    pfnSet, 
    vtPropType, 
    vtsParams) 
```  
  
## <a name="remarks"></a>Hinweise  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Der Name der Klasse.  
  
 `pszName`  
 Externer Name der Eigenschaft.  
  
 `dispid`  
 Die festen DISPID für die Eigenschaft oder Methode.  
  
 `pfnGet`  
 Name der Elementfunktion, die zum Abrufen der Eigenschaft verwendet.  
  
 `pfnSet`  
 Name der Elementfunktion verwendet, um die Eigenschaft festzulegen.  
  
 `memberName`  
 Der Name der Membervariable der Eigenschaft zuordnen  
  
 `vtPropType`  
 Ein Wert, der den Typ der Eigenschaft.  
  
 `vtsParams`  
 Eine Zeichenfolge mit Leerzeichen getrennt VTS_ für jeden Parameter.  
  
## <a name="remarks"></a>Hinweise  
 Diese Makros ermöglichen Ihnen die Angabe einer **DISPID** anstatt MFC automatisch eine zuweisen. Diese erweiterten Makros außer dieser ID an den Makronamen angefügt wird, die denselben Namen haben (z. B. **DISP_PROPERTY_ID**) und die ID wird bestimmt durch den Parameter angegebene direkt nach der `pszName` Parameter. Finden Sie unter AFXDISP. Für Weitere Informationen zu diesen Makros H. Die **_ID** Einträge müssen am Ende der Dispatchzuordnung platziert werden. Sie wirken sich auf die automatische **DISPID** Generation auf die gleiche Weise wie einen nicht-**_ID** Version des Makros würde (die **DISPID**s werden anhand der Position). Zum Beispiel:  
  
```  
BEGIN_DISPATCH_MAP(CDisp3DPoint,
    CCmdTarget)  
    DISP_PROPERTY(CDisp3DPoint, "y",
    m_y,
    VT_I2)  
    DISP_PROPERTY(CDisp3DPoint, "z",
    m_z,
    VT_I2)  
    DISP_PROPERTY_ID(CDisp3DPoint, "x",
    0x00020003,
    m_x,
    VT_I2)  
END_DISPATCH_MAP()  
```  
  
 MFC DISPIDs für Klasse CDisp3DPoint folgendermaßen generiert:  
  
```  
property X    (DISPID)0x00020003  
property Y    (DISPID)0x00000002  
property Z     (DISPID)0x00000001  
```  
  
 Festlegen einer festen **DISPID** eignet sich Abwärtskompatibilität auf eine bereits vorhandene Dispatchschnittstelle oder um bestimmte vom System definierte Methoden oder Eigenschaften zu implementieren (angegeben in der Regel durch eine Negative  **DISPID**, wie z. B. die **DISPID_NEWENUM** Auflistung).  
  
#### <a name="retrieving-the-idispatch-interface-for-a-coleclientitem"></a>Abrufen der IDispatch-Schnittstelle für eine COleClientItem  
 Viele Server unterstützt die Automatisierung in ihrer Document-Objekte zusammen mit der OLE-Server-Funktionen. Um den Zugriff auf diese Automatisierungsschnittstelle zugreifen zu können, es ist notwendig, direkt den Zugriff der **COleClientItem::m_lpObject** Membervariablen gespeichert. Der folgende Code Ruft die `IDispatch` -Schnittstelle für ein Objekt abgeleitet `COleClientItem`. Sie können den folgenden Code in der Anwendung einschließen, wenn Sie diese Funktion erforderlichen finden:  
  
```  
LPDISPATCH CMyClientItem::GetIDispatch()  
{  
    ASSERT_VALID(this);

 ASSERT(m_lpObject != NULL);

 
    LPUNKNOWN lpUnk = m_lpObject;  
 
    Run();
*// must be running  
 
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
    if (lpUnk->QueryInterface(IID_IDispatch, &lpDispatch)   
 != NOERROR)  
 {  
    TRACE0("Warning: does not support IDispatch!\n");

    return NULL;  
 }  
 
    ASSERT(lpDispatch != NULL);

    return lpDispatch;  
}  
```  
  
 Die Dispatchschnittstelle zurückgegeben werden, von dieser Funktion kann dann direkt verwendet oder angefügt eine `COleDispatchDriver` für Typsicherer Zugriff. Wenn Sie es direkt verwenden, stellen Sie sicher, dass Sie aufrufen seine **Version** Member Wenn über den Zeiger (die `COleDispatchDriver` Destruktor wird dies standardmäßig).  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

