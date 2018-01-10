---
title: CConnectionPoint Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
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
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f6a9e9fafc2bbee9959a939815a92c9bc63a650f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
|[CConnectionPoint:: GetIID](#getiid)|Ruft die Schnittstellen-ID von einem Verbindungspunkt ab.|  
|[CConnectionPoint::GetMaxConnections](#getmaxconnections)|Ruft die maximale Anzahl von Verbindungspunkten, die von einem Steuerelement unterstützt.|  
|[CConnectionPoint:: GetNextConnection](#getnextconnection)|Ruft einen Zeiger auf das Verbindungselement auf `pos`.|  
|[CConnectionPoint::GetStartPosition](#getstartposition)|Startet eine Iteration Zuordnung wird durch Zurückgeben einer **POSITION** -Wert, der übergeben werden kann eine `GetNextConnection` aufrufen.|  
|[CConnectionPoint::OnAdvise](#onadvise)|Wird aufgerufen, durch das Framework beim Einrichten oder das Unterbrechen von Clientverbindungen.|  
|[CConnectionPoint::QuerySinkInterface](#querysinkinterface)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|  
  
## <a name="remarks"></a>Hinweise  
 Im Gegensatz zu normalen OLE-Schnittstellen, die zum Implementieren und Verfügbarmachen der Funktionalität eines OLE-Steuerelements verwendet werden, implementiert ein Verbindungspunkt eine Ausgangsschnittstelle, das Initiieren von Aktionen auf andere Objekte, z. B. das Auslösen von Ereignissen und Benachrichtigungen ändern können.  
  
 Eine Verbindung besteht aus zwei Teilen: Objekt beim Aufrufen der Schnittstelle mit dem Namen, der "Quelle" und dem Objekt implementiert die Schnittstelle, die so genannte "Senke". Durch einen Verbindungspunkt verfügbar gemacht werden, kann eine Quelle senken, um Verbindungen mit sich selbst herzustellen. Über den Mechanismus der Connection Point erhält ein Quellobjekt, das einen Zeiger auf die Senke Implementierung eines Satzes von Memberfunktionen. Beispielsweise kann die Quelle zum Auslösen eines Ereignisses, das von der Senke implementiert, die entsprechende Methode der Implementierung die Senke aufrufen.  
  
 Wird standardmäßig ein `COleControl`-abgeleitete Klasse implementiert zwei Verbindungspunkten: eine für Ereignisse und eine für die Eigenschaft änderungsbenachrichtigungen. Diese Verbindungen verwendet werden, bzw. für das Auslösen von Ereignissen und beim Benachrichtigen der Senke (z. B. das Steuerelement-Container) einer-Eigenschaftswert geändert wurde. Auch wird für zusätzliche Verbindungspunkte implementiert OLE-Steuerelemente unterstützt. Für jeden zusätzlichen Verbindungspunkt in der Steuerelementklasse implementiert wird müssen Sie eine "-Verbindungsteil", die den Verbindungspunkt implementiert deklarieren. Wenn Sie eine oder mehrere Verbindungspunkte implementieren, müssen Sie auch eine einzelne "Verbindungstabelle" in der Steuerelementklasse deklarieren.  
  
 Das folgende Beispiel zeigt eine einfache Verbindung zuordnen und einen Verbindungspunkt für die `Sample` OLE-Steuerelements, bestehend aus zwei Codefragmente: der erste Teil deklariert Verbindung Karten- und Punkt; das zweite implementiert diese Karte und Punkt. Das erste Fragment wird in der Deklaration der Steuerelementklasse eingefügt, unter der `protected` Abschnitt:  
  
 [!code-cpp[NVC_MFCConnectionPoints#7](../../mfc/codesnippet/cpp/cconnectionpoint-class_1.h)]  
  
 Die `BEGIN_CONNECTION_PART` und `END_CONNECTION_PART` Makros deklarieren eine eingebettete Klasse `XSampleConnPt` (abgeleitet `CConnectionPoint`), das diesen bestimmten Verbindungspunkt implementiert. Wenn Sie überschreiben möchten `CConnectionPoint` Memberfunktionen oder Hinzufügen von Memberfunktionen von Ihren eigenen, zwischen diesen zwei Makros zu deklarieren. Z. B. die `CONNECTION_IID` Makro überschreibt die `CConnectionPoint::GetIID` Memberfunktion, wenn zwischen diesen beiden Makros platziert.  
  
 Das zweite Codefragment wird in der Implementierungsdatei eingefügt (. CPP) von der Control-Klasse. Dieser Code implementiert die Verbindungstabelle, darunter die zusätzliche Verbindungspunkt `SampleConnPt`:  
  
 [!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/cconnectionpoint-class_2.cpp)]  
  
 Sobald die Codefragmente eingefügt wurden, stellt das Beispiel OLE-Steuerelement einen Verbindungspunkt für die **ISampleSink** Schnittstelle.  
  
 Verbindungspunkte unterstützen in der Regel "Multicasting", die Möglichkeit zum Senden an mehrere senken, die auf die gleiche Schnittstelle verbunden ist. Das folgende Codefragment veranschaulicht, wie Multicasting zu erreichen, indem Sie jede Senke auf einem Verbindungspunkt durchlaufen:  
  
 [!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]  
  
 In diesem Beispiel ruft den aktuellen Satz von Verbindungen ab, auf die `SampleConnPt` Verbindungspunkt mit einem Aufruf von `CConnectionPoint::GetConnections`. Anschließend durchläuft es die Verbindungen und ruft `ISampleSink::SinkFunc` für jede aktive Verbindung.  
  
 Weitere Informationen zur Verwendung von `CConnectionPoint`, finden Sie im Artikel [Verbindungspunkte](../../mfc/connection-points.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CConnectionPoint`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  
  
##  <a name="cconnectionpoint"></a>CConnectionPoint::CConnectionPoint  
 Erstellt ein `CConnectionPoint`-Objekt.  
  
```  
CConnectionPoint();
```  
  
##  <a name="getconnections"></a>CConnectionPoint:: GetConnections  
 Mit dieser Funktion wird zum Abrufen aller aktiven Verbindungen für einen Verbindungspunkt.  
  
```  
const CPtrArray* GetConnections();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Array der aktiven Verbindungen (senken). Einige der Zeiger für das im Array kann NULL sein. Jeder nicht-NULL-Zeiger in dieses Array kann gefahrlos in einen Zeiger auf die Schnittstelle mit einem Umwandlungsoperator konvertiert werden.  
  
##  <a name="getcontainer"></a>CConnectionPoint::GetContainer  
 Wird aufgerufen, durch das Framework zum Abrufen der **IConnectionPointContainer** für den Verbindungspunkt.  
  
```  
virtual LPCONNECTIONPOINTCONTAINER GetContainer();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg, ein Zeiger auf den Container; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist in der Regel implementiert, indem die `BEGIN_CONNECTION_PART` Makro.  
  
##  <a name="getiid"></a>CConnectionPoint:: GetIID  
 Wird aufgerufen, durch das Framework die Schnittstellen-ID eines Verbindungspunktes abgerufen.  
  
```  
virtual REFIID GetIID() = 0;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf den Verbindungspunkt Schnittstellen-ID.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion zum Zurückgeben der Schnittstellen-ID für diese Verbindung an.  
  
##  <a name="getmaxconnections"></a>CConnectionPoint::GetMaxConnections  
 Wird aufgerufen, durch das Framework, um die maximale Anzahl von Verbindungen, die von dem Verbindungspunkt unterstützt abzurufen.  
  
```  
virtual int GetMaxConnections();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Anzahl von Verbindungen, die durch das Steuerelement, oder -1 unterstützt wird, wenn keine Beschränkung.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung gibt-1 zurück, die keine Begrenzung zurück.  
  
 Überschreiben Sie diese Funktion, wenn Sie die Anzahl der senken, die dem Steuerelement eine Verbindung herstellen können, einschränken möchten.  
  
##  <a name="getnextconnection"></a>CConnectionPoint:: GetNextConnection  
 Ruft einen Zeiger auf das Verbindungselement auf `pos`.  
  
```  
LPUNKNOWN GetNextConnection(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Gibt einen Verweis auf eine **POSITION** von einem vorherigen zurückgegebene Wert `GetNextConnection` oder [GetStartPosition](#getstartposition) aufrufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Verbindungselement gemäß `pos`, oder NULL.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist besonders hilfreich für die Iteration durch alle Elemente in der Zuordnung für die Verbindung. Beim Überspringen von dieser Funktion zurückgegebenen NULL-Werte.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]  
  
##  <a name="getstartposition"></a>CConnectionPoint::GetStartPosition  
 Startet eine Iteration Zuordnung wird durch Zurückgeben einer **POSITION** -Wert, der übergeben werden kann ein [GetNextConnection](#getnextconnection) aufrufen.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** Wert, der eine Startposition für die Karte; durchlaufen angibt oder **NULL** , wenn die Zuordnung leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Sequenz Iteration ist nicht vorhersagbar; Daher muss der "ersten Element in der Zuordnung" keine andere besonderen Bedeutung.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CConnectionPoint:: GetNextConnection](#getnextconnection).  
  
##  <a name="onadvise"></a>CConnectionPoint::OnAdvise  
 Wird aufgerufen, durch das Framework beim Herstellen einer Verbindung wird hergestellt oder unterbrochen wird.  
  
```  
virtual void OnAdvise(BOOL bAdvise);
```  
  
### <a name="parameters"></a>Parameter  
 `bAdvise`  
 **"True"**, wenn eine Verbindung hergestellt ist, andernfalls wird **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung wird keine Aktion ausgeführt.  
  
 Überschreiben Sie diese Funktion, wenn senken anschließen oder trennen Sie Ihre Verbindungspunkt Benachrichtigung werden soll.  
  
##  <a name="querysinkinterface"></a>CConnectionPoint::QuerySinkInterface  
 Ruft einen Zeiger auf die angeforderte Schnittstelle ab.  
  
```  
virtual HRESULT QuerySinkInterface(
    LPUNKNOWN pUnkSink,  
    void** ppInterface);
```  
  
### <a name="parameters"></a>Parameter  
 `pUnkSink`  
 Der Bezeichner der Senkenschnittstelle angefordert wird.  
  
 `ppInterface`  
 Ein Zeiger auf den Schnittstellenzeiger, der durch `pUnkSink`. Wenn das Objekt nicht über diese Schnittstelle unterstützt \* `ppInterface` festgelegt ist, um **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)

