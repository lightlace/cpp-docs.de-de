---
title: Verbindungszuordnungen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- connection maps
ms.assetid: 1f25a9bc-6d09-4614-99cf-dc38e8ddfa73
caps.latest.revision: 12
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 8947930d20cc65075abe442b233e4c086f10f76e
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="connection-maps"></a>Verbindungszuordnungen
OLE-Steuerelemente können Schnittstellen für andere Anwendungen verfügbar zu machen. Diese Schnittstellen ermöglichen nur Zugriff von einem Container in dieses Steuerelement. Wenn Zugriff auf externe Schnittstellen von anderen OLE-Objekten ist ein OLE-Steuerelement möchte, muss ein Verbindungspunkt hergestellt werden. Verbindungspunkt ermöglicht ein ausgehender Zugriff auf externe Dispatch-Karten, z. B. ereigniszuordnungen oder Benachrichtigungsfunktionen Steuerelement.  
  
 Die Microsoft Foundation Class-Bibliothek bietet ein Programmiermodell, die Verbindungspunkte unterstützt. In diesem Modell "maps Verbindung" werden verwendet, um Schnittstellen oder Verbindungspunkte für OLE-Steuerelements festzulegen. Verbindungszuordnungen enthalten ein Makro für jeden Verbindungspunkt. Weitere Informationen zum verbindungszuordnungen, finden Sie unter der [CConnectionPoint](../../mfc/reference/cconnectionpoint-class.md) Klasse.  
  
 In der Regel wird ein Steuerelement nur zwei Verbindungspunkte unterstützen: eine für Ereignisse und eine Eigenschaft Benachrichtigungen. Diese implementiert werden, indem die `COleControl` Basisklasse und erfordern keine zusätzliche Arbeit vom Steuerelement Writer. Weitere Punkte, die Sie in Ihrer Klasse implementieren möchten, müssen manuell hinzugefügt werden. Um verbindungszuordnungen und Punkte zu unterstützen, stellt MFC die folgenden Makros:  
  
### <a name="connection-map-declaration-and-demarcation"></a>Verbindungsdeklaration und Demarkation  
  
|||  
|-|-|  
|[BEGIN_CONNECTION_PART](#begin_connection_part)|Deklariert eine eingebettete Klasse, die einen zusätzliche Verbindungspunkt implementiert (muss in der Klassendeklaration verwendet werden).|  
|[END_CONNECTION_PART](#end_connection_part)|Beendet die Deklaration eines Verbindungspunktes (muss in der Klassendeklaration verwendet werden).|  
|[CONNECTION_IID](#connection_iid)|Gibt die Schnittstellen-ID des Verbindungspunkts des Steuerelements an.|  
|[DECLARE_CONNECTION_MAP](#declare_connection_map)|Deklariert, dass eine Zuordnung für die Verbindung in einer Klasse verwendet wird (muss in der Klassendeklaration verwendet werden).|  
|[BEGIN_CONNECTION_MAP](#begin_connection_map)|Der Beginn der Definition der Verbindungstabelle (muss in der klassenimplementierung verwendet werden).|  
|[END_CONNECTION_MAP](#end_connection_map)|Beendet die Definition der Verbindungstabelle (muss in der klassenimplementierung verwendet werden).|  
|[CONNECTION_PART](#connection_part)|Gibt einen Verbindungspunkt in der Verbindungstabelle des Steuerelements an.|  
  
 Die folgenden Funktionen unterstützen eine Senke herstellen und Trennen einer Verbindung, die Verwendung von Verbindungspunkten:  
  
### <a name="initializationtermination-of-connection-points"></a>Initialisierung bzw. der Beendigung der Verbindungspunkte  
  
|||  
|-|-|  
|[AfxConnectionAdvise](#afxconnectionadvise)|Stellt eine Verbindung zwischen einer Quelle und Senke.|  
|[AfxConnectionUnadvise](#afxconnectionunadvise)|Unterbricht die Verbindung zwischen einer Quelle und Senke.|  
  
##  <a name="begin_connection_part"></a>BEGIN_CONNECTION_PART  
 Verwenden der `BEGIN_CONNECTION_PART` Makro, um die Definition der zusätzliche Verbindungspunkte über die Verbindungspunkte Ereignis- und Benachrichtigung zu beginnen.  
  
```   
BEGIN_CONNECTION_PART(theClass, localClass)   
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Gibt an, dass der Name der Control-Klasse, deren Verbindung zeigen dies, ist.  
  
 *localClass*  
 Gibt den Namen der lokalen Klasse, die den Verbindungspunkt implementiert.  
  
### <a name="remarks"></a>Hinweise  
 In der Deklaration (. h)-Datei, die Memberfunktionen für die Klasse definiert, starten Sie den Verbindungspunkt mit der `BEGIN_CONNECTION_PART` -Makro, fügen Sie dann die `CONNECTION_IID` -Makro und andere Memberfunktionen implementieren, und schließen den Punkt Verbindungstabelle mit soll die `END_CONNECTION_PART` Makro.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="end_connection_part"></a>END_CONNECTION_PART  
 Die Deklaration der Verbindungspunkt wird beendet.  
  
```   
END_CONNECTION_PART(localClass)   
```  
  
### <a name="parameters"></a>Parameter  
 *localClass*  
 Gibt den Namen der lokalen Klasse, die den Verbindungspunkt implementiert.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="connection_iid"></a>CONNECTION_IID  
 Verwenden Sie zwischen dem `BEGIN_CONNECTION_PART` und `END_CONNECTION_PART` Makros definieren eine Schnittstellen-ID für einen Verbindungspunkt unterstützt das OLE-Steuerelement.  
  
```   
CONNECTION_IID(iid)   
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 Die Schnittstellen-ID der Schnittstelle, die von den Verbindungspunkt aufgerufen.  
  
### <a name="remarks"></a>Hinweise  
 Die `iid` Argument ist eine Schnittstelle, die ID verwendet, um die Schnittstelle zu identifizieren, die der Verbindungspunkt für die verbundene senken aufruft. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCConnectionPoints&#10;](../../mfc/codesnippet/cpp/connection-maps_1.h)]  
  
 Gibt einen Verbindungspunkt, der Aufrufe an die `ISinkInterface` Schnittstelle.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="declare_connection_map"></a>DECLARE_CONNECTION_MAP  
 Jede `COleControl`-abgeleiteten Klasse in Ihrem Programm bieten Verbindungstabelle um zusätzliche anzugeben, die das Steuerelement unterstützt.  
  
```   
DECLARE_CONNECTION_MAP() 
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Steuerelement weitere Punkte unterstützt, die `DECLARE_CONNECTION_MAP` Makro am Ende der Klassendeklaration. Verwenden Sie dann in der CPP-Datei, die die Member-Funktionen für die Klasse definiert die `BEGIN_CONNECTION_MAP` -Makro, `CONNECTION_PART` Makros für jede von Verbindungspunkten für das Steuerelement, und die `END_CONNECTION_MAP` Makro, um das Ende der Verbindungstabelle deklarieren.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="begin_connection_map"></a>BEGIN_CONNECTION_MAP  
 Jede `COleControl`-abgeleiteten Klasse in Ihrem Programm bieten Verbindungstabelle um Verbindungspunkte anzugeben, die vom Steuerelement nicht unterstützt wird.  
  
```   
BEGIN_CONNECTION_MAP(theClass, theBase)   
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Gibt an, dass der Name der Control-Klasse, deren Verbindung zuzuordnen, dies, ist.  
  
 *theBase*  
 Gibt den Namen der Basisklasse des `theClass`.  
  
### <a name="remarks"></a>Hinweise  
 In der Implementierung (. CPP)-Datei, die Memberfunktionen für die Klasse definiert, starten die Zuordnung der Verbindung mit der `BEGIN_CONNECTION_MAP` -Makro, fügen Sie dann Makroeinträge für jedes Ihrer Verbindung mit der [CONNECTION_PART](#connection_part) Makro. Schließen Sie die Zuordnung der Verbindung mit der [END_CONNECTION_MAP](#end_connection_map) Makro.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="end_connection_map"></a>END_CONNECTION_MAP  
 Beendet die Definition der Zuordnung Verbindung.  
  
```   
END_CONNECTION_MAP()  
```  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="connection_part"></a>CONNECTION_PART  
 Ordnet einen Verbindungspunkt für das OLE-Steuerelement zu einer bestimmten Schnittstelle-ID.  
  
```   
CONNECTION_PART(theClass, iid, localClass)   
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Gibt an, dass der Name der Control-Klasse, deren Verbindung zeigen dies, ist.  
  
 `iid`  
 Die Schnittstellen-ID der Schnittstelle, die von den Verbindungspunkt aufgerufen.  
  
 *localClass*  
 Gibt den Namen der lokalen Klasse, die den Verbindungspunkt implementiert.  
  
### <a name="remarks"></a>Hinweise  
 Zum Beispiel:  
  
 [!code-cpp[NVC_MFCConnectionPoints&#2;](../../mfc/codesnippet/cpp/connection-maps_2.cpp)]  
  
 implementiert die Verbindungstabelle, einem Verbindungspunkt, die Aufrufe der `IID_ISinkInterface` Schnittstelle.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="afxconnectionadvise"></a>AfxConnectionAdvise  
 Rufen Sie diese Funktion, um eine Verbindung zwischen einer Quelle, die durch angegebene `pUnkSrc`, und eine Spüle, angegeben durch `pUnkSink`.  
  
```   
BOOL AFXAPI AfxConnectionAdvise(
    LPUNKNOWN pUnkSrc, 
    REFIID iid, 
    LPUNKNOWN pUnkSink, 
    BOOL bRefCount, 
    DWORD FAR* pdwCookie);
```  
  
### <a name="parameters"></a>Parameter  
 `pUnkSrc`  
 Ein Zeiger auf das Objekt, das die Schnittstelle aufruft.  
  
 `pUnkSink`  
 Ein Zeiger auf das Objekt, das die Schnittstelle implementiert.  
  
 `iid`  
 Die Schnittstellen-ID der Verbindung.  
  
 `bRefCount`  
 **True,** gibt an, dass das Erstellen der Verbindung den Verweiszähler des verursachen `pUnkSink` erhöht werden soll. **FALSE** gibt an, dass der Verweiszähler nicht erhöht werden soll.  
  
 `pdwCookie`  
 Ein Zeiger auf eine `DWORD` , in dem eine Verbindungs-ID zurückgegeben wird. Dieser Wert sollte übergeben werden, als die `dwCookie` Parameter `AfxConnectionUnadvise` beim Trennen der Verbindungs.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn eine Verbindung hergestellt wurde; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCConnectionPoints&#8;](../../mfc/codesnippet/cpp/connection-maps_3.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxctl.h 

##  <a name="afxconnectionunadvise"></a>AfxConnectionUnadvise  
 Mit dieser Funktion können Sie eine Verbindung zwischen einer Quelle, angegeben durch Trennen `pUnkSrc`, und eine Spüle, angegeben durch `pUnkSink`.  
  
```   
BOOL AFXAPI AfxConnectionUnadvise(
    LPUNKNOWN pUnkSrc, 
    REFIID iid, 
    LPUNKNOWN pUnkSink, 
    BOOL bRefCount, 
    DWORD dwCookie); 
```  
  
### <a name="parameters"></a>Parameter  
 `pUnkSrc`  
 Ein Zeiger auf das Objekt, das die Schnittstelle aufruft.  
  
 `pUnkSink`  
 Ein Zeiger auf das Objekt, das die Schnittstelle implementiert.  
  
 `iid`  
 Die Schnittstellen-ID die Verbindungspunkt-Schnittstelle.  
  
 `bRefCount`  
 **True,** gibt an, dass das Trennen der Verbindung den Verweiszähler des verursachen `pUnkSink` dekrementiert werden soll. **FALSE** gibt an, dass der Verweiszähler nicht verringert werden soll.  
  
 `dwCookie`  
 Die Verbindungs-ID, die von zurückgegebenen `AfxConnectionAdvise`.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn eine Verbindung getrennt wurde; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCConnectionPoints&#9;](../../mfc/codesnippet/cpp/connection-maps_4.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxctl.h 

## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

