---
title: CConnectionPoint Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CConnectionPoint
dev_langs:
- C++
helpviewer_keywords:
- CConnectionPoint class
ms.assetid: f0f23a1e-5e8c-41a9-aa6c-1a4793b28e8f
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a511f252bf921433d070059518e6e67b952680eb
ms.lasthandoff: 02/24/2017

---
# <a name="cconnectionpoint-class"></a>CConnectionPoint-Klasse
Definiert einen besonderen Schnittstellentyp, "Verbindungspunkt" genannt, der verwendet wird, um mit anderen OLE-Objekten zu kommunizieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CConnectionPoint : public CCmdTarget  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CConnectionPoint::CConnectionPoint](#cconnectionpoint)|Erstellt ein `CConnectionPoint`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CConnectionPoint:: GetConnections](#getconnections)|Ruft alle Verbindungspunkte in einer Zuordnung Verbindung ab.|  
|[CConnectionPoint::GetContainer](#getcontainer)|Ruft den Container des Steuerelements, das die Verbindungstabelle besitzt.|  
|[CConnectionPoint:: GetIID](#getiid)|Ruft die Schnittstellen-ID eines Verbindungspunkts ab.|  
|[CConnectionPoint::GetMaxConnections](#getmaxconnections)|Ruft die maximale Anzahl von Verbindungspunkten, die von einem Steuerelement unterstützt.|  
|[CConnectionPoint:: GetNextConnection](#getnextconnection)|Ruft einen Zeiger auf das Verbindungselement am `pos`.|  
|[CConnectionPoint::GetStartPosition](#getstartposition)|Startet eine Zuordnung Iteration durch die Rückgabe einer **POSITION** -Wert, der an übergeben werden kann ein `GetNextConnection` aufrufen.|  
|[CConnectionPoint::OnAdvise](#onadvise)|Aufgerufen, wenn einrichten oder das Unterbrechen von Clientverbindungen.|  
|[CConnectionPoint::QuerySinkInterface](#querysinkinterface)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|  
  
## <a name="remarks"></a>Hinweise  
 Im Gegensatz zu normalen OLE-Schnittstellen, die zum Implementieren und machen die Funktionalität des OLE-Steuerelement verwendet werden, implementiert einen Verbindungspunkt für eine Ausgangsschnittstelle, die zum Initiieren von Aktionen auf andere Objekte, z. B. das Auslösen von Ereignissen und Benachrichtigungen ändern können.  
  
 Eine Verbindung besteht aus zwei Teilen: der Aufruf die Klassenschnittstelle, die "Source" und das Objekt, das die-Schnittstelle implementieren, Objekt aufgerufen "Sink". Durch das Offenlegen eines Verbindungspunkts, ermöglicht es die Quelle Empfängern, eine Verbindung mit sich selbst herzustellen. Durch den Verbindungspunktmechanismus erhält ein Quellobjekt einen Zeiger auf die Senke Implementierung eines Satzes von Memberfunktionen. Beispielsweise kann die Quelle zum Auslösen eines Ereignisses von der Senke implementiert die entsprechende Methode der Implementierung des Empfängers aufrufen.  
  
 In der Standardeinstellung eine `COleControl`-abgeleitete Klasse implementiert zwei Verbindungspunkten: eine für Ereignisse und eine für die Eigenschaft änderungsbenachrichtigungen. Diese Verbindungen werden verwendet, bzw. für das Auslösen von Ereignissen und benachrichtigt eine Senke (z. B. der Container des Steuerelements) Wenn ein Eigenschaftswert geändert wurde. Auch wird für zusätzliche Verbindungspunkte implementiert OLE-Steuerelemente unterstützt. Für jeden zusätzlichen Verbindungspunkt in der Steuerelementklasse implementiert deklarieren Sie einen "Verbindungsteil", der den Verbindungspunkt implementiert. Wenn Sie eine oder mehrere Verbindungspunkte implementieren, müssen Sie auch ein einzelnes "Verbindungstabelle" in der Steuerelementklasse zu deklarieren.  
  
 Das folgende Beispiel zeigt eine einfache Verbindungstabelle und einen Verbindungspunkt für die `Sample` OLE-Steuerelement, bestehend aus zwei Codefragmente: der erste Teil deklariert, der Verbindungstabelle und Verbindungspunkt; die zweite implementiert diese Zuordnung und Punkt. Das erste Fragment eingefügt wird die Deklaration der Steuerelementklasse, unter der `protected` Abschnitt:  
  
 [!code-cpp[NVC_MFCConnectionPoints&#7;](../../mfc/codesnippet/cpp/cconnectionpoint-class_1.h)]  
  
 Die `BEGIN_CONNECTION_PART` und `END_CONNECTION_PART` deklarieren die eingebettete Klasse `XSampleConnPt` (abgeleitet von `CConnectionPoint`), die diesen bestimmten Verbindungspunkt implementiert. Wenn Sie überschreiben möchten `CConnectionPoint` Memberfunktionen oder eigene Memberfunktionen hinzufügen, müssen sie zwischen diesen beiden Makros deklariert werden. Zum Beispiel die `CONNECTION_IID` Makro überschreibt die `CConnectionPoint::GetIID` Memberfunktion, wenn zwischen diesen beiden Makros platziert.  
  
 Im zweiten Beispiel befindet sich in der Implementierungsdatei (. CPP) der Steuerelementklasse. Dieser Code implementiert die Verbindungstabelle, einschließlich den zusätzlichen Verbindungspunkt `SampleConnPt`:  
  
 [!code-cpp[NVC_MFCConnectionPoints&#2;](../../mfc/codesnippet/cpp/cconnectionpoint-class_2.cpp)]  
  
 Sobald Codefragmente eingefügt wurden, stellt das Beispiel OLE-Steuerelement einen Verbindungspunkt für die **ISampleSink** Schnittstelle.  
  
 Verbindungspunkte unterstützen in der Regel "Multicasting", die Möglichkeit, senden Sie an mehrere Empfänger mit derselben Schnittstelle verbunden ist. Das folgende Codefragment veranschaulicht, wie Multicasting zu erreichen, indem Sie jede Senke an einem Verbindungspunkt durchlaufen:  
  
 [!code-cpp[NVC_MFCConnectionPoints&4;](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]  
  
 Dieses Beispiel ruft den aktuellen Satz von Verbindungen auf die `SampleConnPt` Verbindungspunkt mit einem Aufruf von `CConnectionPoint::GetConnections`. Anschließend durchläuft es die Verbindung und ruft `ISampleSink::SinkFunc` für jede aktive Verbindung.  
  
 Weitere Informationen zur Verwendung von `CConnectionPoint`, finden Sie im Artikel [Verbindungspunkte](../../mfc/connection-points.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CConnectionPoint`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  
  
##  <a name="a-namecconnectionpointa--cconnectionpointcconnectionpoint"></a><a name="cconnectionpoint"></a>CConnectionPoint::CConnectionPoint  
 Erstellt ein `CConnectionPoint`-Objekt.  
  
```  
CConnectionPoint();
```  
  
##  <a name="a-namegetconnectionsa--cconnectionpointgetconnections"></a><a name="getconnections"></a>CConnectionPoint:: GetConnections  
 Rufen Sie diese Funktion, um alle aktiven Verbindungen für einen Verbindungspunkt abzurufen.  
  
```  
const CPtrArray* GetConnections();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Array der aktiven Verbindungen (senken). Einige der Zeiger in das Array kann NULL sein. Jeder nicht-NULL-Zeiger in diesem Array kann gefahrlos in einen Zeiger auf die Ereignissenken-Schnittstelle mit einem Umwandlungsoperator konvertiert werden.  
  
##  <a name="a-namegetcontainera--cconnectionpointgetcontainer"></a><a name="getcontainer"></a>CConnectionPoint::GetContainer  
 Aufgerufen, zum Abrufen der **IConnectionPointContainer** für den Verbindungspunkt.  
  
```  
virtual LPCONNECTIONPOINTCONTAINER GetContainer();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, ein Zeiger auf den Container; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist in der Regel implementiert, durch die `BEGIN_CONNECTION_PART` Makro.  
  
##  <a name="a-namegetiida--cconnectionpointgetiid"></a><a name="getiid"></a>CConnectionPoint:: GetIID  
 Aufgerufen, um die Schnittstellen-ID eines Verbindungspunkts abzurufen.  
  
```  
virtual REFIID GetIID() = 0;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf den Verbindungspunkt-Schnittstellen-ID.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um die Schnittstellen-ID für den Verbindungspunkt zurück.  
  
##  <a name="a-namegetmaxconnectionsa--cconnectionpointgetmaxconnections"></a><a name="getmaxconnections"></a>CConnectionPoint::GetMaxConnections  
 Aufgerufen, um die maximale Anzahl von Verbindungen, die von den Verbindungspunkt unterstützt abzurufen.  
  
```  
virtual int GetMaxConnections();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Anzahl von Verbindungen unterstützt durch das Steuerelement, oder -1, wenn keine Beschränkung.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung gibt-1 zurück, keine Begrenzung.  
  
 Überschreiben Sie diese Funktion, wenn Sie möchten die Anzahl der senken zu beschränken, die mit dem Steuerelement verbunden werden kann.  
  
##  <a name="a-namegetnextconnectiona--cconnectionpointgetnextconnection"></a><a name="getnextconnection"></a>CConnectionPoint:: GetNextConnection  
 Ruft einen Zeiger auf das Verbindungselement am `pos`.  
  
```  
LPUNKNOWN GetNextConnection(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Gibt einen Verweis auf eine **POSITION** von einem vorherigen zurückgegebene Wert `GetNextConnection` oder [GetStartPosition](#getstartposition) aufrufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die angegebene Verbindungselement `pos`, oder NULL.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist besonders hilfreich für die Iteration durch alle Elemente in der Verbindungstabelle. Beim Fahren Sie alle NULL-Werte von dieser Funktion zurückgegeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCConnectionPoints&4;](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]  
  
##  <a name="a-namegetstartpositiona--cconnectionpointgetstartposition"></a><a name="getstartposition"></a>CConnectionPoint::GetStartPosition  
 Startet eine Zuordnung Iteration durch die Rückgabe einer **POSITION** -Wert, der an übergeben werden kann ein [GetNextConnection](#getnextconnection) aufrufen.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** Wert an der Position des ersten Durchlaufen der Karte; oder **NULL** , wenn die Zuordnung leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Reihenfolge der Iteration ist nicht vorhersagbar. "erste Element in der Zuordnung" hat daher keine besondere Bedeutung.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CConnectionPoint:: GetNextConnection](#getnextconnection).  
  
##  <a name="a-nameonadvisea--cconnectionpointonadvise"></a><a name="onadvise"></a>CConnectionPoint::OnAdvise  
 Aufgerufen, wenn eine Verbindung wird aufgebaut oder unterbrochen.  
  
```  
virtual void OnAdvise(BOOL bAdvise);
```  
  
### <a name="parameters"></a>Parameter  
 `bAdvise`  
 **True,**, wenn eine Verbindung eingerichtet wurde; andernfalls wird **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung wird keine Aktion ausgeführt.  
  
 Überschreiben Sie diese Funktion, wenn senken anschließen oder Trennen der Verbindungspunkt Benachrichtigung werden soll.  
  
##  <a name="a-namequerysinkinterfacea--cconnectionpointquerysinkinterface"></a><a name="querysinkinterface"></a>CConnectionPoint::QuerySinkInterface  
 Ruft einen Zeiger auf die angeforderte Schnittstelle ab.  
  
```  
virtual HRESULT QuerySinkInterface(
    LPUNKNOWN pUnkSink,  
    void** ppInterface);
```  
  
### <a name="parameters"></a>Parameter  
 `pUnkSink`  
 Der Bezeichner für die Senkenschnittstelle angefordert wird.  
  
 `ppInterface`  
 Ein Zeiger auf den Schnittstellenzeiger vom `pUnkSink`. Wenn das Objekt diese Schnittstelle nicht unterstützt \* `ppInterface` Wert **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)


