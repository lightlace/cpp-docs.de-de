---
title: "TN039: MFC/OLE-Automatisierungsimplementierung | Microsoft Docs"
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
  - "Automatisierung, MFC COM-Schnittstelleneingabepunkte"
  - "IDispatch-Schnittstelle"
  - "MFC, COM-Unterstützung"
  - "MFC, OLE DB und"
  - "TN039"
ms.assetid: 765fa3e9-dd54-4f08-9ad2-26e0546ff8b6
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# TN039: MFC/OLE-Automatisierungsimplementierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert.  Daher können einige Verfahren und Themen veraltet oder falsch sein.  Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
## Übersicht von IDispatch Schnittstelle OLE  
 Die `IDispatch`\-Schnittstelle ist die Möglichkeit, durch die Anwendungen so Methoden und Eigenschaften verfügbar machen, dass andere Anwendungen wie Visual Basic oder andere Sprachen, die Funktionen der Anwendung nutzen können.  Der wichtigste Teil dieser Schnittstelle ist die **IDispatch::Invoke**\-Funktion.  MFC verwendet "Dispatchzuordnungen", **IDispatch::Invoke** verwendet.  Die Dispatchzuordnung stellt die MFC\-Implementierungsinformationen auf das Layout oder "Form" der von `CCmdTarget` abgeleiteten Klassen, so, dass die Eigenschaften des Objekts direkt bearbeiten können, bereit oder ruft Memberfunktionen innerhalb des Objekts auf, um **IDispatch::Invoke** Anforderungen zu erfüllen.  
  
 In den meisten Fällen arbeitet Der Klassen\-Assistent und MFC zusammen, um die meisten Details der OLE\-Automatisierung vom Anwendungsprogrammierer auszublenden.  Der Programmierer werden die tatsächlichen Funktionen, die in der Anwendung verfügbar gemacht und muss sich nicht um die zugrunde liegende Verkabelung kümmern.  
  
 Es gibt Fälle jedoch wenn es erforderlich ist, zu verstehen, die MFC im Hintergrund macht.  Dieser Hinweis anspricht, wie das Framework **DISPID**s zu Memberfunktionen und Eigenschaften zuweisen.  Kenntnisse der Verwendung des Algorithmus MFC zum Zuweisen von **DISPID**s ist nur erforderlich, wenn Sie die IDs wissen müssen, z, wenn Sie eine "Typbibliothek" für Objekte der Anwendung erstellen.  
  
## Zuweisung DISPID MFC  
 Obwohl der Endbenutzer mit Automatisierungsserver \(ein Visual Basic\-Benutzer, beispielsweise\), die tatsächlichen Namen der Automatisierung aktivierten Eigenschaften und Methoden in ihrem Code \(z obj.ShowWindow\) erkennt, empfängt die Implementierung von **IDispatch::Invoke** nicht die tatsächlichen Namen.  Für Optimierungsgründe erhält sie **DISPID**, das ein 32\-Bit\-" Magic Cookie" ist, das die Methode oder Eigenschaft beschreibt, auf die zugegriffen werden soll.  **DISPID** Diese Werte werden von der `IDispatch` \- Implementierung durch eine andere Methode zurückgegeben, genannt **IDispatch::GetIDsOfNames**.  Eine Automatisierungsclientanwendung ruft `GetIDsOfNames` einmal für jeden Member oder Eigenschaft auf, die sie vorgesehen zuzugreifen und speichert sie für neuere **IDispatch::Invoke**\- Aufrufe zwischen.  Dadurch, die teure Zeichenfolgensuche ist nur einmal pro Objektverwendung, und nicht einmal pro Aufruf **IDispatch::Invoke** ausgeführt.  
  
 MFC bestimmt das **DISPID**s für jede Methode und Eigenschaft basierend auf zwei Dinge:  
  
-   Der Abstand zwischen dem oberen Rand der Dispatchzuordnung Verwandter \(1\)  
  
-   Der Abstand der Dispatchzuordnung von der am stärksten abgeleiteten Klasse Verwandter \(0\)  
  
 **DISPID** wird in zwei Teilen.  **LOWORDDISPID** enthält die erste Komponente, den Abstand zwischen dem oberen Rand der Dispatchzuordnung.  **HIWORD** enthält den Abstand von der am stärksten abgeleiteten Klasse.  Beispiel:  
  
```  
class CDispPoint : public CCmdTarget  
{  
public:  
    short m_x, m_y;  
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
  
BEGIN_DISPATCH_MAP(CDispPoint, CCmdTarget)  
    DISP_PROPERTY(CDispPoint, "x", m_x, VT_I2)  
    DISP_PROPERTY(CDispPoint, "y", m_y, VT_I2)  
END_DISPATCH_MAP()  
  
BEGIN_DISPATCH_MAP(CDisp3DPoint, CDispPoint)  
    DISP_PROPERTY(CDisp3DPoint, "z", m_z, VT_I2)  
END_DISPATCH_MAP()  
```  
  
 Wie Sie sehen, gibt es zwei Klassen, die OLE\-Automatisierungs\-Schnittstellen verfügbar machen.  Eine dieser Klassen wird von der anderen abgeleitet und folglich die Funktionen der Basisklasse, einschließlich des OLE\-Automatisierungs\-Teil nutzt \(x\- "" und "y " Eigenschaften in diesem Fall\).  
  
 MFC generiert **DISPID**s für Klasse CDispPoint, wie folgt:  
  
```  
property X    (DISPID)0x00000001  
property Y    (DISPID)0x00000002  
```  
  
 Da die Eigenschaften in einer Basisklasse nicht sind, ist **HIWORDDISPID** immer null \(der Abstand von der am stärksten abgeleiteten Klasse für CDispPoint ist null\).  
  
 MFC generiert **DISPID**s für Klasse CDisp3DPoint, wie folgt:  
  
```  
property Z    (DISPID)0x00000001  
property X    (DISPID)0x00010001  
property Y    (DISPID)0x00010002  
```  
  
 Die Z\-Eigenschaft wird **DISPID** mit null **HIWORD** angegeben, wie es in der Klasse, die die Eigenschaften verfügbar macht, CDisp3DPoint definiert wird.  Da den x\- und Y\-Eigenschaften werden in einer Basisklasse, **HIWORDDISPID** ist 1, seit der Klasse, in der diese Eigenschaften ist in einem bestimmten Abstand von einer Ableitung von der am stärksten abgeleiteten Klasse definiert werden.  
  
> [!NOTE]
>  **LOWORD** wird immer durch die Position in der Zuordnung bestimmt, wenn Einträge in der Zuordnung mit explizitem **DISPID** vorhanden sind \(siehe nächsten Abschnitt zu Informationen über das **\_ID**\-Versionen der Makros `DISP_PROPERTY` und `DISP_FUNCTION` \).  
  
## Erweiterte MFC\-Dispatchzuordnungs\-Funktionen  
 Es gibt verschiedene weitere Funktionen, die die nicht in dieser Version von Visual C\+\+ unterstützt.  Der Klassen\-Assistent unterstützt `DISP_FUNCTION`, `DISP_PROPERTY` und `DISP_PROPERTY_EX`, die eine Methode, eine Membervariableneigenschaft definieren und\/eine Funktionseigenschaft des festgelegten Members, bzw. abrufen.  Diese Funktionen sind normalerweise alle, die erforderlich ist, um die meisten Automatisierungsserver zu erstellen.  
  
 Die folgenden zusätzlichen Makros können verwendet werden, wenn die die unterstützten Makros nicht angemessen sind: `DISP_PROPERTY_NOTIFY` und `DISP_PROPERTY_PARAM`.  
  
## DISP\_PROPERTY\_NOTIFY \- Makrobeschreibung  
  
```  
  
        DISP_PROPERTY_NOTIFY(   
   theClass,   
   pszName,   
   memberName,   
   pfnAfterSet,   
   vtPropType   
)  
```  
  
## Hinweise  
  
### Parameter  
 `theClass`  
 Name der Klasse.  
  
 `pszName`  
 Externer Name der Eigenschaft.  
  
 `memberName`  
 Name der Membervariable, in der die Eigenschaft gespeichert wird.  
  
 `pfnAfterSet`  
 Name der Memberfunktion, der aufgerufen werden soll, wenn Eigenschaft geändert wird.  
  
 `vtPropType`  
 Ein Wert, der den Typ der Eigenschaft an.  
  
## Hinweise  
 Dieses Makro ist ähnlich wie `DISP_PROPERTY`, außer dass es akzeptiert ein zusätzliches Argument.  Das zusätzliche Argument, *pfnAfterSet,* sollte eine Memberfunktion sein, die ausschließlich zurückgibt und keine Parameter annimmt, OnPropertyNotify\(\) "null".  Sie wird aufgerufen, **nachdem** die Membervariable geändert wurde.  
  
## DISP\_PROPERTY\_PARAM \- Makrobeschreibung  
  
```  
  
        DISP_PROPERTY_PARAM(   
   theClass,  
   pszName,  
   pfnGet,  
   pfnSet,  
   vtPropType,  
   vtsParams   
)  
```  
  
## Hinweise  
  
### Parameter  
 `theClass`  
 Name der Klasse.  
  
 `pszName`  
 Externer Name der Eigenschaft.  
  
 `memberGet`  
 Name der Memberfunktion verwendet, um die Eigenschaft abzurufen.  
  
 `memberSet`  
 Name der Memberfunktion verwendet, um die Eigenschaft festzulegen.  
  
 `vtPropType`  
 Ein Wert, der den Typ der Eigenschaft an.  
  
 `vtsParams`  
 Eine Zeichenfolge des Leerzeichens getrennt VTS\_ für jeden Parameter.  
  
## Hinweise  
 Ähnlich wie das `DISP_PROPERTY_EX`\-Makro wird in Makro eine Eigenschaft, die mit separatem zugegriffen wird, abrufen und des festgelegten Members Funktionen.  Dieses Makro können Sie jedoch, um einer Parameterliste für die Eigenschaft an.  Dies ist für die Implementierung von Eigenschaften sinnvoll, die auf andere Weise indiziert oder parametrisiert werden.  Die Parameter immer zuerst platziert, gefolgt durch den neuen Wert für die Eigenschaft.  Beispiel:  
  
```  
DISP_PROPERTY_PARAM(CMyObject, "item", GetItem, SetItem, VT_DISPATCH,    VTS_I2 VTS_I2)  
```  
  
 würde entsprechen, abzurufen und um Features des festgelegten Members:  
  
```  
LPDISPATCH CMyObject::GetItem(short row, short col)  
void CMyObject::SetItem(short row, short col, LPDISPATCH newValue)  
```  
  
## DISP\_XXXX\_ID \- Makrobeschreibungen  
  
```  
  
        DISP_FUNCTION_ID(   
   theClass,  
   pszName,  
   dispid,  
   pfnMember,  
   vtRetVal,  
   vtsParams   
) DISP_PROPERTY_ID(   
   theClass,  
   pszName,  
   dispid,  
   memberName,  
   vtPropType   
) DISP_PROPERTY_NOTIFY_ID(   
   theClass,  
   pszName,  
   dispid,  
   memberName,  
   pfnAfterSet,  
   vtPropType   
) DISP_PROPERTY_EX_ID(   
   theClass,  
   pszName,  
   dispid,  
   pfnGet,  
   pfnSet,  
   vtPropType   
) DISP_PROPERTY_PARAM_ID(   
   theClass,  
   pszName,  
   dispid,  
   pfnGet,  
   pfnSet,  
   vtPropType,  
   vtsParams   
)  
```  
  
## Hinweise  
  
### Parameter  
 `theClass`  
 Name der Klasse.  
  
 `pszName`  
 Externer Name der Eigenschaft.  
  
 `dispid`  
 Das festgelegte DISPID für die Eigenschaft oder Methode.  
  
 `pfnGet`  
 Name der Memberfunktion verwendet, um die Eigenschaft abzurufen.  
  
 `pfnSet`  
 Name der Memberfunktion verwendet, um die Eigenschaft festzulegen.  
  
 `memberName`  
 Der Name der der Eigenschaft zuzuweisen Membervariable,  
  
 `vtPropType`  
 Ein Wert, der den Typ der Eigenschaft an.  
  
 `vtsParams`  
 Eine Zeichenfolge des Leerzeichens getrennt VTS\_ für jeden Parameter.  
  
## Hinweise  
 Diese Makros bieten die Möglichkeit, **DISPID**, anstatt, MFC werden, anzugeben zuweisen automatisch ein.  Diese erweiterte Makros haben die gleichen Namen, außer dass ID wird dem Makronamen angefügt \(z.  **DISP\_PROPERTY\_ID**\) und die ID wird vom Parameter ermittelt, der gleich nach dem Parameter `pszName` angegeben wird.  Siehe AFXDISP.H weitere Informationen zu diesen Makros.  Die **\_ID** Einträge müssen am Ende der Dispatchzuordnung platziert werden.  Sie beeinflussen die automatische **DISPID** Generation, ebenso wie eine Nicht\-**\_ID**\-Version des Makros wurde \(das **DISPID**s werden durch die Position festgelegt\).  Beispiel:  
  
```  
BEGIN_DISPATCH_MAP(CDisp3DPoint, CCmdTarget)  
    DISP_PROPERTY(CDisp3DPoint, "y", m_y, VT_I2)  
    DISP_PROPERTY(CDisp3DPoint, "z", m_z, VT_I2)  
    DISP_PROPERTY_ID(CDisp3DPoint, "x", 0x00020003, m_x, VT_I2)  
END_DISPATCH_MAP()  
```  
  
 MFC generiert DISPID für Klasse CDisp3DPoint, wie folgt:  
  
```  
property X    (DISPID)0x00020003  
property Y    (DISPID)0x00000002  
property Z     (DISPID)0x00000001  
```  
  
 Festen **DISPID** festzulegen ist nützlich, die Abwärtskompatibilität zu einer bereits vorhandenen Dispatchschnittstelle beizubehalten, oder das Implementieren definierte bestimmtes System die Methoden oder Eigenschaften \(normalerweise angegeben durch negatives **DISPID**, wie die **DISPID\_NEWENUM**\-Auflistung\).  
  
#### Abrufen der IDispatch\-Schnittstelle für ein COleClientItem  
 Viele Server unterstützen Automatisierung in ihrer Dokumentobjekte, zusammen mit der OLE\-Serverfunktionalität.  Um zu dieser Automatisierungsschnittstelle zu erhalten, müssen auf die **COleClientItem::m\_lpObject**\-Membervariable direkt zugreifen.  Der Code unten wird die `IDispatch`\-Schnittstelle für ein Objekt ab, das von `COleClientItem` abgeleitet wird.  Sie können den folgenden Code in die Anwendung aufnehmen, wenn die erforderliche Funktionalität finden:  
  
```  
LPDISPATCH CMyClientItem::GetIDispatch()  
{  
    ASSERT_VALID(this);  
    ASSERT(m_lpObject != NULL);  
  
    LPUNKNOWN lpUnk = m_lpObject;  
  
    Run();    // must be running  
  
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
  
 Die Dispatchschnittstelle, die von dieser Funktion zurückgegeben wurde, könnte dann direkt verwendet werden oder `COleDispatchDriver` für typsicheren Zugriff angefügt werden.  Wenn Sie diese direkt verwenden, überprüfen Sie, ob Sie deren Member von **Version** wenn mit den Zeiger aufrufen \(Destruktor der `COleDispatchDriver` führt dies standardmäßig\).  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)