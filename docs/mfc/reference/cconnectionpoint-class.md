---
title: CConnectionPoint-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CConnectionPoint
- AFXDISP/CConnectionPoint
- AFXDISP/CConnectionPoint::CConnectionPoint
- AFXDISP/CConnectionPoint::GetConnections
- AFXDISP/CConnectionPoint::GetContainer
- AFXDISP/CConnectionPoint::GetIID
- AFXDISP/CConnectionPoint::GetMaxConnections
- AFXDISP/CConnectionPoint::GetNextConnection
- AFXDISP/CConnectionPoint::GetStartPosition
- AFXDISP/CConnectionPoint::OnAdvise
- AFXDISP/CConnectionPoint::QuerySinkInterface
dev_langs:
- C++
helpviewer_keywords:
- CConnectionPoint [MFC], CConnectionPoint
- CConnectionPoint [MFC], GetConnections
- CConnectionPoint [MFC], GetContainer
- CConnectionPoint [MFC], GetIID
- CConnectionPoint [MFC], GetMaxConnections
- CConnectionPoint [MFC], GetNextConnection
- CConnectionPoint [MFC], GetStartPosition
- CConnectionPoint [MFC], OnAdvise
- CConnectionPoint [MFC], QuerySinkInterface
ms.assetid: f0f23a1e-5e8c-41a9-aa6c-1a4793b28e8f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b092c6a097d39c3114193c578bc37c179ca0df7
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336198"
---
# <a name="cconnectionpoint-class"></a>CConnectionPoint-Klasse
Definiert einen besonderen Schnittstellentyp, "Verbindungspunkt" genannt, der verwendet wird, um mit anderen OLE-Objekten zu kommunizieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CConnectionPoint : public CCmdTarget  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CConnectionPoint::CConnectionPoint](#cconnectionpoint)|Erstellt ein `CConnectionPoint`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CConnectionPoint:: GetConnections](#getconnections)|Ruft alle Verbindungspunkte in einer Zuordnung für die Verbindung ab.|  
|[CConnectionPoint::GetContainer](#getcontainer)|Ruft den Container des Steuerelements, das die Zuordnung für die Verbindung besitzt.|  
|[CConnectionPoint:: GetIID](#getiid)|Ruft die Schnittstellen-ID eines Verbindungspunkts ab.|  
|[CConnectionPoint::GetMaxConnections](#getmaxconnections)|Ruft die maximale Anzahl von Verbindungspunkten, die von einem Steuerelement unterstützt.|  
|[CConnectionPoint:: GetNextConnection](#getnextconnection)|Ruft einen Zeiger auf das Verbindungselement auf *pos*.|  
|[CConnectionPoint::GetStartPosition](#getstartposition)|Startet eine Iteration für die Zuordnung durch Rückgabe eines Werts von POSITION, die übergeben werden kann eine `GetNextConnection` aufrufen.|  
|[CConnectionPoint::OnAdvise](#onadvise)|Wird aufgerufen, durch das Framework beim Einrichten oder Unterbrechen von Verbindungen.|  
|[CConnectionPoint::QuerySinkInterface](#querysinkinterface)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|  
  
## <a name="remarks"></a>Hinweise  
 Im Gegensatz zu normalen OLE-Schnittstellen, die zum Implementieren und machen die Funktionalität des OLE-Steuerelements verwendet werden, implementiert einen Verbindungspunkt für eine ausgehende-Schnittstelle, die zum Initiieren von Aktionen auf andere Objekte, z. B. das Auslösen von Ereignissen und Benachrichtigungen ändern kann.  
  
 Eine Verbindung besteht aus zwei Teilen: das Objekt, das Aufrufen der Schnittstelle namens "Source", und das Objekt, das die-Schnittstelle implementieren, die Senke aufgerufen haben "." Durch einen Verbindungspunkt verfügbar zu machen, kann eine Quelle senken, um Verbindungen mit sich selbst herzustellen. Über den Verbindungspunktmechanismus erhält ein Quellobjekt einen Zeiger auf die Senke in der Implementierung eines Satzes von Memberfunktionen. Beispielsweise kann die Quelle zum Auslösen eines Ereignisses, das von der Senke implementiert, die entsprechende Methode der Senke der Implementierung aufrufen.  
  
 Standardmäßig eine `COleControl`-abgeleitete Klasse implementiert zwei Verbindungspunkten: eine für Ereignisse und eine für die Eigenschaft änderungsbenachrichtigungen. Diese Verbindungen werden verwendet, bzw. für das Auslösen von Ereignissen und benachrichtigt eine Senke (z. B. im Container des Steuerelements) Wenn ein Eigenschaftswert geändert wurde. Auch wird für OLE-Steuerelemente zum Implementieren von Verbindungspunkten zusätzliche unterstützt. Für jeden zusätzlichen Verbindungspunkt, der in der Steuerelementklasse implementiert ist deklarieren Sie "Verbindung Part", die den Verbindungspunkt implementiert. Wenn Sie eine oder mehrere Verbindungspunkte implementieren, müssen Sie auch ein einzelnes "Verbindungs-Karte" in der Steuerelementklasse deklarieren.  
  
 Das folgende Beispiel zeigt eine einfache Verbindung zuordnen und einen Verbindungspunkt für die `Sample` OLE-Steuerelements, bestehend aus zwei Codefragmente: der erste Teil deklariert, die Zuordnung der Verbindung und den Punkt; die zweite implementiert diese Zuordnung und Punkt. Das erste Fragment wird in der Deklaration der Steuerelementklasse eingefügt, unter dem **geschützt** Abschnitt:  
  
 [!code-cpp[NVC_MFCConnectionPoints#7](../../mfc/codesnippet/cpp/cconnectionpoint-class_1.h)]  
  
 Die BEGIN_CONNECTION_PART und END_CONNECTION_PART deklarieren einer eingebetteten Klasse `XSampleConnPt` (abgeleitet `CConnectionPoint`), die diesem bestimmten Verbindungspunkt implementiert. Wenn Sie überschreiben möchten `CConnectionPoint` Memberfunktionen oder Memberfunktionen eigene hinzufügen, müssen sie zwischen diesen beiden Makros deklariert werden. Die CONNECTION_IID-Makro überschreibt z. B. die `CConnectionPoint::GetIID` Memberfunktion, wenn Sie zwischen diesen beiden Makros platziert.  
  
 Das zweite Codefragment in der Implementierungsdatei eingefügt (. CPP) der Steuerelementklasse. Dieser Code implementiert Verbindung Code Map, die zusätzliche Verbindungspunkt enthält, `SampleConnPt`:  
  
 [!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/cconnectionpoint-class_2.cpp)]  
  
 Sobald die Codefragmente eingefügt wurden, stellt das Beispiel OLE-Steuerelement einen Verbindungspunkt für die `ISampleSink` Schnittstelle.  
  
 In der Regel unterstützt Verbindungspunkte "Multicasting", die die Möglichkeit zum Senden an mehrere senken, die auf die gleiche Schnittstelle verbunden ist. Das folgende Codefragment veranschaulicht das Multicasting zu erreichen, indem Sie jede Senke an einem Verbindungspunkt durchlaufen:  
  
 [!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]  
  
 In diesem Beispiel ruft den aktuellen Satz von Verbindungen ab, auf die `SampleConnPt` Verbindungspunkt mit einem Aufruf von `CConnectionPoint::GetConnections`. Anschließend durchläuft es die Verbindungen und ruft `ISampleSink::SinkFunc` auf jedes aktive Verbindung.  
  
 Weitere Informationen zur Verwendung von `CConnectionPoint`, finden Sie im Artikel [Verbindungspunkte](../../mfc/connection-points.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CConnectionPoint`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  
  
##  <a name="cconnectionpoint"></a>  CConnectionPoint::CConnectionPoint  
 Erstellt ein `CConnectionPoint`-Objekt.  
  
```  
CConnectionPoint();
```  
  
##  <a name="getconnections"></a>  CConnectionPoint:: GetConnections  
 Rufen Sie diese Funktion, um alle aktiven Verbindungen für einen Verbindungspunkt abzurufen.  
  
```  
const CPtrArray* GetConnections();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Array der aktiven Verbindungen (senken). Einige der Zeiger in das Array kann NULL sein. Jede nicht-NULL-Zeiger in diesem Array kann problemlos in einen Zeiger auf die Ereignissenken-Schnittstelle, die mit einem Umwandlungsoperator konvertiert werden.  
  
##  <a name="getcontainer"></a>  CConnectionPoint::GetContainer  
 Wird aufgerufen, durch das Framework zum Abrufen der `IConnectionPointContainer` für den Verbindungspunkt.  
  
```  
virtual LPCONNECTIONPOINTCONTAINER GetContainer();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg einen Zeiger auf den Container andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist in der Regel durch das BEGIN_CONNECTION_PART-Makro implementiert.  
  
##  <a name="getiid"></a>  CConnectionPoint:: GetIID  
 Wird aufgerufen, durch das Framework die Schnittstellen-ID eines Verbindungspunkts abrufen.  
  
```  
virtual REFIID GetIID() = 0;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf die Verbindungspunkt Schnittstellen-ID.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion zum Zurückgeben der Schnittstellen-ID für diese Verbindung an.  
  
##  <a name="getmaxconnections"></a>  CConnectionPoint::GetMaxConnections  
 Wird aufgerufen, durch das Framework, um die maximale Anzahl von Verbindungen, die vom Verbindungspunkt unterstützt abzurufen.  
  
```  
virtual int GetMaxConnections();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Anzahl von Verbindungen, die von dem Steuerelement oder -1 unterstützt, wenn keine Beschränkung.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung gibt-1 zurück, keine Begrenzung.  
  
 Überschreiben Sie diese Funktion, wenn Sie die Anzahl der senken, die dem Steuerelement eine Verbindung herstellen können, einschränken möchten.  
  
##  <a name="getnextconnection"></a>  CConnectionPoint:: GetNextConnection  
 Ruft einen Zeiger auf das Verbindungselement auf *pos*.  
  
```  
LPUNKNOWN GetNextConnection(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *POS*  
 Gibt einen Verweis auf eine Positionswert, der von einem vorherigen zurückgegebene `GetNextConnection` oder [GetStartPosition](#getstartposition) aufrufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Verbindungselement gemäß *pos*, oder NULL.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist besonders hilfreich für die Iteration durch alle Elemente in der Zuordnung für die Verbindung. Beim durchlaufen, überspringen Sie alle von dieser Funktion zurückgegebenen NULL-Werte.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]  
  
##  <a name="getstartposition"></a>  CConnectionPoint::GetStartPosition  
 Startet eine Iteration für die Zuordnung durch Rückgabe eines Werts von POSITION, die übergeben werden kann eine [GetNextConnection](#getnextconnection) aufrufen.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Positionswert, der Position des ersten Durchlaufen der Zuordnung angibt; oder NULL, wenn die Zuordnung leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Sequenz der Iteration ist nicht vorhersagbar; der "ersten Element in der Zuordnung" hat daher keine besondere Bedeutung.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CConnectionPoint:: GetNextConnection](#getnextconnection).  
  
##  <a name="onadvise"></a>  CConnectionPoint::OnAdvise  
 Wird aufgerufen, durch das Framework beim Herstellen einer Verbindung wird aufgebaut oder unterbrochen.  
  
```  
virtual void OnAdvise(BOOL bAdvise);
```  
  
### <a name="parameters"></a>Parameter  
 *bAdvise*  
 TRUE, wenn eine Verbindung erstellt wird. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung wird keine Aktion ausgeführt.  
  
 Überschreiben Sie diese Funktion, wenn senken anschließen oder trennen Ihre Verbindungspunkt Benachrichtigung werden soll.  
  
##  <a name="querysinkinterface"></a>  CConnectionPoint::QuerySinkInterface  
 Ruft einen Zeiger auf die angeforderte Schnittstelle ab.  
  
```  
virtual HRESULT QuerySinkInterface(
    LPUNKNOWN pUnkSink,  
    void** ppInterface);
```  
  
### <a name="parameters"></a>Parameter  
 *pUnkSink*  
 Der Bezeichner der die Ereignissenken-Schnittstelle angefordert wird.  
  
 *ppInterface*  
 Ein Zeiger auf den Schnittstellenzeiger vom *pUnkSink*. Wenn das Objekt nicht über diese Schnittstelle unterstützt \* *PpInterface* auf NULL festgelegt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)

