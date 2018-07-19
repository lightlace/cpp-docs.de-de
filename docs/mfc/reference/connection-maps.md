---
title: Verbindungszuordnungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- connection maps
ms.assetid: 1f25a9bc-6d09-4614-99cf-dc38e8ddfa73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 015dce59058f776269c3c793b195a323eae2f652
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850601"
---
# <a name="connection-maps"></a>Verbindungszuordnungen
OLE-Steuerelemente können Schnittstellen für andere Anwendungen verfügbar zu machen. Diese Schnittstellen können nur den Zugriff aus einem Container in das Steuerelement. Wenn möchte, dass ein OLE-Steuerelements Zugriff auf externe Schnittstellen von anderen OLE-Objekten, muss die Verbindung hergestellt werden. Diesem Verbindungspunkt kann ein Steuerelement ausgehenden Zugriff auf externe Dispatchzuordnungen, z. B. ereigniszuordnungen oder Benachrichtigungsfunktionen.  
  
 Die Microsoft Foundation Class-Bibliothek bietet ein Programmiermodell, das Verbindungspunkte unterstützt. In diesem Modell "maps Verbindung" werden verwendet, um die Schnittstellen oder Verbindungspunkte für das OLE-Steuerelement zu kennzeichnen. Verbindungszuordnungen enthalten ein Makro für jeden Verbindungspunkt. Weitere Informationen zu verbindungszuordnungen, finden Sie unter den [CConnectionPoint](../../mfc/reference/cconnectionpoint-class.md) Klasse.  
  
 In der Regel wird ein Steuerelement nur zwei Verbindungspunkte unterstützen: eine für Ereignisse und eine Eigenschaft Benachrichtigungen. Diese implementiert werden, indem die `COleControl` Basisklasse und erfordern keine zusätzliche Arbeit vom Steuerelement-Writer. Zusätzliche Verbindungsparameter Punkte, die Sie in Ihrer Klasse implementieren möchten, müssen manuell hinzugefügt werden. Verbindungszuordnungen und Punkte zur Unterstützung bietet MFC die folgenden Makros:  
  
### <a name="connection-map-declaration-and-demarcation"></a>Verbindung Zuordnung Deklaration und Demarkation  
  
|||  
|-|-|  
|[BEGIN_CONNECTION_PART](#begin_connection_part)|Deklariert eine eingebettete-Klasse, die einen zusätzliche Verbindungspunkt implementiert (muss in der Klassendeklaration verwendet werden).|  
|[END_CONNECTION_PART](#end_connection_part)|Beendet die Deklaration eines Verbindungspunktes (muss in der Klassendeklaration verwendet werden).|  
|[CONNECTION_IID](#connection_iid)|Gibt an, die Schnittstellen-ID des Steuerelements an.|  
|[DECLARE_CONNECTION_MAP](#declare_connection_map)|Deklariert, dass eine Zuordnung für die Verbindung in einer Klasse verwendet wird (muss in der Klassendeklaration verwendet werden).|  
|[BEGIN_CONNECTION_MAP](#begin_connection_map)|Der Beginn der Definition der Verbindungstabelle (muss in der klassenimplementierung verwendet werden).|  
|[END_CONNECTION_MAP](#end_connection_map)|Beendet die Definition der Verbindungstabelle (muss in der klassenimplementierung verwendet werden).|  
|[CONNECTION_PART](#connection_part)|Gibt einen Verbindungspunkt in der Verbindungstabelle des Steuerelements an.|  
  
 Die folgenden Funktionen unterstützen eine Senke herstellen und Trennen einer Verbindung mithilfe von Verbindungspunkten:  
  
### <a name="initializationtermination-of-connection-points"></a>Initialisierung bzw. der Beendigung von Verbindungspunkten  
  
|||  
|-|-|  
|[AfxConnectionAdvise](#afxconnectionadvise)|Herstellen einer Verbindung zwischen einer Quelle und Senke.|  
|[AfxConnectionUnadvise](#afxconnectionunadvise)|Wird eine Verbindung zwischen einer Quelle und Senke an.|  
  
##  <a name="begin_connection_part"></a>  BEGIN_CONNECTION_PART  
 Verwenden Sie das BEGIN_CONNECTION_PART-Makro, um die Definition der zusätzlichen Verbindungspunkte über die Verbindungspunkte der Ereignis- und Benachrichtigung zu beginnen.  
  
```   
BEGIN_CONNECTION_PART(theClass, localClass)   
```  
  
### <a name="parameters"></a>Parameter  
 *theClass*  
 Gibt an, die Control-Klasse, deren Verbindungspunkt dies, heißt.  
  
 *localClass*  
 Gibt den Namen der lokalen Klasse, die den Verbindungspunkt implementiert.  
  
### <a name="remarks"></a>Hinweise  
 Starten Sie in der (. h)-Deklarationsdatei, die die Member-Funktionen für die Klasse definiert wird den Verbindungspunkt mit dem BEGIN_CONNECTION_PART-Makro, und klicken Sie dann fügen Sie die CONNECTION_IID-Makro und alle anderen Memberfunktionen, die Sie implementieren möchten hinzu und schließen Sie die Verbindung Zeigen Sie die Zuordnung mit dem END_CONNECTION_PART-Makro.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="end_connection_part"></a>  END_CONNECTION_PART  
 Beendet die Deklaration von Ihrem Verbindungspunkt an.  
  
```   
END_CONNECTION_PART(localClass)   
```  
  
### <a name="parameters"></a>Parameter  
 *localClass*  
 Gibt den Namen der lokalen Klasse, die den Verbindungspunkt implementiert.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="connection_iid"></a>  CONNECTION_IID  
 Verwenden Sie zwischen dem BEGIN_CONNECTION_PART und END_CONNECTION_PART Makros um eine Schnittstellen-ID für einen Verbindungspunkt unterstützt durch das OLE-Steuerelement zu definieren.  
  
```   
CONNECTION_IID(iid)   
```  
  
### <a name="parameters"></a>Parameter  
 *IID*  
 Die Schnittstellen-ID der Schnittstelle wird von den Verbindungspunkt aufgerufen werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die *Iid* Argument ist eine Schnittstelle, die ID verwendet, um die Schnittstelle zu identifizieren, die der Verbindungspunkt für die verbundene senken aufruft. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCConnectionPoints#10](../../mfc/codesnippet/cpp/connection-maps_1.h)]  
  
 Gibt an, einem Verbindungspunkt, der Aufrufe der `ISinkInterface` Schnittstelle.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="declare_connection_map"></a>  DECLARE_CONNECTION_MAP  
 Jede `COleControl`-abgeleiteten Klasse in Ihrem Programm bieten eine Zuordnung der Verbindung zur Angabe der zusätzlichen Verbindungspunkte, die das Steuerelement unterstützt.  
  
```   
DECLARE_CONNECTION_MAP() 
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Steuerelement weitere Punkte unterstützt, verwenden Sie das DECLARE_CONNECTION_MAP-Makro am Ende der Klassendeklaration. Verwenden Sie dann in der CPP-Datei, die die Member-Funktionen für die Klasse definiert die BEGIN_CONNECTION_MAP-Makro, CONNECTION_PART-Makros für jede von Verbindungspunkten des Steuerelements und der END_CONNECTION_MAP-Makro zum Deklarieren der am Ende der Zuordnung für die Verbindung ein.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="begin_connection_map"></a>  BEGIN_CONNECTION_MAP  
 Jede `COleControl`-abgeleiteten Klasse in Ihrem Programm bieten eine Zuordnung der Verbindung zur Angabe der Verbindungspunkte, die vom Steuerelement nicht unterstützt wird.  
  
```   
BEGIN_CONNECTION_MAP(theClass, theBase)   
```  
  
### <a name="parameters"></a>Parameter  
 *theClass*  
 Gibt an, dass der Name der Steuerelement-Klasse, dessen Verbindung eine Zuordnung, ist.  
  
 *theBase*  
 Gibt den Namen der Basisklasse der *TheClass*.  
  
### <a name="remarks"></a>Hinweise  
 In der Implementierung (. CPP)-Datei, die den Member-Funktionen für die Klasse, starten Sie die Zuordnung für die Verbindung mit dem BEGIN_CONNECTION_MAP-Makro, und fügen Sie die Makroeinträge für jede Ihrer Verbindungspunkte, die mit der [CONNECTION_PART](#connection_part) Makro. Schließen Sie am Ende der Zuordnung der Verbindung mit der [END_CONNECTION_MAP](#end_connection_map) Makro.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="end_connection_map"></a>  END_CONNECTION_MAP  
 Beendet die Definition der Zuordnung Verbindung an.  
  
```   
END_CONNECTION_MAP()  
```  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="connection_part"></a>  CONNECTION_PART  
 Ordnet einen Verbindungspunkt für das OLE-Steuerelement eine bestimmte Schnittstellen-ID.  
  
```   
CONNECTION_PART(theClass, iid, localClass)   
```  
  
### <a name="parameters"></a>Parameter  
 *theClass*  
 Gibt an, die Control-Klasse, deren Verbindungspunkt dies, heißt.  
  
 *IID*  
 Die Schnittstellen-ID der Schnittstelle wird von den Verbindungspunkt aufgerufen werden soll.  
  
 *localClass*  
 Gibt den Namen der lokalen Klasse, die den Verbindungspunkt implementiert.  
  
### <a name="remarks"></a>Hinweise  
 Zum Beispiel:  
  
 [!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/connection-maps_2.cpp)]  
  
 implementiert eine Zuordnung Verbindung mit einem Verbindungspunkt, die Aufrufe der `IID_ISinkInterface` Schnittstelle.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="afxconnectionadvise"></a>  AfxConnectionAdvise  
 Mit dieser Funktion wird zum Herstellen einer Verbindung zwischen einer Quelle, die anhand des *pUnkSrc*, und eine Senke, die anhand des *pUnkSink*.  
  
```   
BOOL AFXAPI AfxConnectionAdvise(
    LPUNKNOWN pUnkSrc, 
    REFIID iid, 
    LPUNKNOWN pUnkSink, 
    BOOL bRefCount, 
    DWORD FAR* pdwCookie);
```  
  
### <a name="parameters"></a>Parameter  
 *pUnkSrc*  
 Ein Zeiger auf das Objekt, das die Schnittstelle aufruft.  
  
 *pUnkSink*  
 Ein Zeiger auf das Objekt, das die Schnittstelle implementiert.  
  
 *IID*  
 Die Schnittstellen-ID der Verbindung.  
  
 *bRefCount*  
 TRUE gibt an, dass das Herstellen der Verbindung den Verweiszähler des verursachen *pUnkSink* inkrementiert werden soll. FALSE gibt an, dass der Verweiszähler nicht erhöht werden soll.  
  
 *pdwCookie*  
 Ein Zeiger auf einen DWORD-Wert, in denen eine Verbindungs-ID zurückgegeben wird. Dieser Wert sollte übergeben werden, als die *DwCookie* Parameter `AfxConnectionUnadvise` beim Trennen der Verbindungs.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn eine Verbindung hergestellt wurde, andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCConnectionPoints#8](../../mfc/codesnippet/cpp/connection-maps_3.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxctl.h 

##  <a name="afxconnectionunadvise"></a>  AfxConnectionUnadvise  
 Mit dieser Funktion wird zum Trennen einer Verbindungs zwischen einer Quelle, die anhand des *pUnkSrc*, und eine Senke, die anhand des *pUnkSink*.  
  
```   
BOOL AFXAPI AfxConnectionUnadvise(
    LPUNKNOWN pUnkSrc, 
    REFIID iid, 
    LPUNKNOWN pUnkSink, 
    BOOL bRefCount, 
    DWORD dwCookie); 
```  
  
### <a name="parameters"></a>Parameter  
 *pUnkSrc*  
 Ein Zeiger auf das Objekt, das die Schnittstelle aufruft.  
  
 *pUnkSink*  
 Ein Zeiger auf das Objekt, das die Schnittstelle implementiert.  
  
 *IID*  
 Die Schnittstellen-ID, der die Verbindungspunkt-Schnittstelle.  
  
 *bRefCount*  
 TRUE gibt an, dass die Verbindung getrennt wird den Verweiszähler des verursachen *pUnkSink* dekrementiert werden soll. FALSE gibt an, dass der Verweiszähler nicht dekrementiert werden soll.  
  
 *dwCookie*  
 Der Verbindungsbezeichner zurückgegebenes `AfxConnectionAdvise`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn eine Verbindung getrennt wurde, andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCConnectionPoints#9](../../mfc/codesnippet/cpp/connection-maps_4.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxctl.h 

## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
