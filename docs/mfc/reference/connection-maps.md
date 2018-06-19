---
title: Verbindungszuordnungen | Microsoft Docs
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
ms.openlocfilehash: 475314edba2a11535349991db644a4915e352ae7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372837"
---
# <a name="connection-maps"></a>Verbindungszuordnungen
OLE-Steuerelemente sind in der Lage, Schnittstellen für andere Anwendungen verfügbar zu machen. Diese Schnittstellen können nur den Zugriff auf einen Container, in das entsprechende Steuerelement. Wenn ein OLE-Steuerelements externe Schnittstellen von anderen OLE-Objekte zugreifen möchte, muss ein Verbindungspunkt eingerichtet werden. Diese Verbindungspunkt kann ein Steuerelement ausgehenden Zugriff auf externe Dispatchzuordnungen, z. B. ereigniszuordnungen oder Benachrichtigungsfunktionen.  
  
 Die Microsoft Foundation Class-Bibliothek bietet ein Programmiermodell, die Verbindungspunkte unterstützt. In diesem Modell "ordnet Verbindung" werden verwendet, um Schnittstellen oder Verbindungspunkte für die OLE-Steuerelements zu kennzeichnen. Verbindungszuordnungen enthalten ein Makro für jeden Verbindungspunkt. Weitere Informationen zu verbindungszuordnungen, finden Sie unter der [CConnectionPoint](../../mfc/reference/cconnectionpoint-class.md) Klasse.  
  
 In der Regel wird ein Steuerelement nur zwei Verbindungspunkte unterstützen: eine für Ereignisse und eine Eigenschaft Benachrichtigungen. Diese implementiert werden, indem die `COleControl` Basisklasse und erfordern keine weiteren Schritte vom Steuerelement Writer. Keine zusätzliche Verbindungsparameter Punkte, die Sie in Ihrer Klasse implementieren möchten, müssen manuell hinzugefügt werden. Verbindungszuordnungen und Punkte zur Unterstützung bietet MFC die folgenden Makros:  
  
### <a name="connection-map-declaration-and-demarcation"></a>Verbindung Zuordnung Deklaration und Demarkation  
  
|||  
|-|-|  
|[BEGIN_CONNECTION_PART](#begin_connection_part)|Deklariert eine eingebettete-Klasse, die einen zusätzliche Verbindungspunkt implementiert (muss in der Klassendeklaration verwendet werden).|  
|[END_CONNECTION_PART](#end_connection_part)|Beendet die Deklaration eines Verbindungspunktes (muss in der Klassendeklaration verwendet werden).|  
|[CONNECTION_IID](#connection_iid)|Gibt an, der Schnittstellen-ID des Verbindungspunkts des Steuerelements.|  
|[DECLARE_CONNECTION_MAP](#declare_connection_map)|Deklariert, dass die Zuordnung einer Verbindung in einer Klasse verwendet wird (muss in der Klassendeklaration verwendet werden).|  
|[BEGIN_CONNECTION_MAP](#begin_connection_map)|Startet die Definition der Verbindungstabelle (muss in der klassenimplementierung verwendet werden).|  
|[END_CONNECTION_MAP](#end_connection_map)|Beendet die Definition der Verbindungstabelle (muss in der klassenimplementierung verwendet werden).|  
|[CONNECTION_PART](#connection_part)|Gibt einen Verbindungspunkt in der Verbindungstabelle des Steuerelements an.|  
  
 Die folgenden Funktionen werden Senke beim Herstellen oder trennen eine Verbindung mit der Verbindungspunkte unterstützen:  
  
### <a name="initializationtermination-of-connection-points"></a>Initialisierung/Beendigung von Verbindungspunkten  
  
|||  
|-|-|  
|[AfxConnectionAdvise](#afxconnectionadvise)|Herstellen einer Verbindung zwischen einer Quelle und Senke.|  
|[AfxConnectionUnadvise](#afxconnectionunadvise)|Wird eine Verbindung zwischen einer Quelle und Senke unterbrochen.|  
  
##  <a name="begin_connection_part"></a>  BEGIN_CONNECTION_PART  
 Verwenden der `BEGIN_CONNECTION_PART` Makro, um die Definition der zusätzliche Verbindungspunkte hinter der Benachrichtigung-Verbindungspunkte Ereignis und eine Eigenschaft zu beginnen.  
  
```   
BEGIN_CONNECTION_PART(theClass, localClass)   
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Gibt an, dass der Name der Steuerelementklasse, deren Verbindung zeigen dies.  
  
 *localClass*  
 Gibt den Namen der lokalen Klasse, die den Verbindungspunkt implementiert.  
  
### <a name="remarks"></a>Hinweise  
 In der Deklaration (. h)-Datei, die Memberfunktionen für die Klasse definiert, starten Sie den Verbindungspunkt mit dem `BEGIN_CONNECTION_PART` -Makro, fügen Sie dann die `CONNECTION_IID` Makro angehalten und eine andere Memberfunktionen Sie implementieren, und schließen die Verbindung Punkt Zuordnung möchten mit der `END_CONNECTION_PART` Makro.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="end_connection_part"></a>  END_CONNECTION_PART  
 Die Deklaration der Verbindungspunkt wird beendet.  
  
```   
END_CONNECTION_PART(localClass)   
```  
  
### <a name="parameters"></a>Parameter  
 *localClass*  
 Gibt den Namen der lokalen Klasse, die den Verbindungspunkt implementiert.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="connection_iid"></a>  CONNECTION_IID  
 Verwenden Sie zwischen den `BEGIN_CONNECTION_PART` und `END_CONNECTION_PART` Makros definieren eine Schnittstellen-ID für einen Verbindungspunkt von OLE-Steuerelements unterstützt.  
  
```   
CONNECTION_IID(iid)   
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 Der Schnittstellen-ID der Schnittstelle, die von dem Verbindungspunkt aufgerufen werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die `iid` Argument ist eine Schnittstelle, die ID verwendet wird, um die Schnittstelle zu identifizieren, die der Verbindungspunkt für die verbundenen senken aufruft. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCConnectionPoints#10](../../mfc/codesnippet/cpp/connection-maps_1.h)]  
  
 Gibt einen Verbindungspunkt, der Aufrufe an die `ISinkInterface` Schnittstelle.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="declare_connection_map"></a>  DECLARE_CONNECTION_MAP  
 Jede `COleControl`-abgeleiteten Klasse in Ihrem Programm bieten eine Zuordnung Verbindung, um zusätzliche Verbindungspunkte anzugeben, die das Steuerelement unterstützt.  
  
```   
DECLARE_CONNECTION_MAP() 
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Steuerelement die zusätzliche Punkte unterstützt, verwenden die `DECLARE_CONNECTION_MAP` Makro am Ende der Klassendeklaration. Verwenden Sie dann in der CPP-Datei, die die Memberfunktionen für die Klasse definiert die `BEGIN_CONNECTION_MAP` Makro `CONNECTION_PART` Makros für die einzelnen Verbindungspunkte für das Steuerelement, und die `END_CONNECTION_MAP` Makro, um das Ende der Zuordnung der Verbindung zu deklarieren.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="begin_connection_map"></a>  BEGIN_CONNECTION_MAP  
 Jede `COleControl`-abgeleiteten Klasse in Ihrem Programm bieten eine Zuordnung der Verbindung um Verbindungspunkte anzugeben, die das Steuerelement unterstützt.  
  
```   
BEGIN_CONNECTION_MAP(theClass, theBase)   
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Gibt an, dass der Name der Steuerelementklasse, deren Verbindung ordnen.  
  
 *theBase*  
 Gibt den Namen der Basisklasse der `theClass`.  
  
### <a name="remarks"></a>Hinweise  
 In der Implementierung (. Starten Sie CPP)-Datei, die Memberfunktionen für die Klasse definiert, die Zuordnung der Verbindung mit der `BEGIN_CONNECTION_MAP` -Makro, fügen Sie dann die Makroeinträge für jede Ihrer Verbindungspunkte mithilfe der [CONNECTION_PART](#connection_part) Makro. Schließen Sie am Ende der Zuordnung der Verbindung mit der [END_CONNECTION_MAP](#end_connection_map) Makro.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="end_connection_map"></a>  END_CONNECTION_MAP  
 Die Definition der Zuordnung Verbindung wird beendet.  
  
```   
END_CONNECTION_MAP()  
```  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="connection_part"></a>  CONNECTION_PART  
 Ordnet einen Verbindungspunkt für die OLE-Steuerelements zu einer bestimmten Schnittstelle-ID  
  
```   
CONNECTION_PART(theClass, iid, localClass)   
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Gibt an, dass der Name der Steuerelementklasse, deren Verbindung zeigen dies.  
  
 `iid`  
 Der Schnittstellen-ID der Schnittstelle, die von dem Verbindungspunkt aufgerufen werden soll.  
  
 *localClass*  
 Gibt den Namen der lokalen Klasse, die den Verbindungspunkt implementiert.  
  
### <a name="remarks"></a>Hinweise  
 Zum Beispiel:  
  
 [!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/connection-maps_2.cpp)]  
  
 implementiert eine Verbindung-Zuordnung mit einem Verbindungspunkt, die aufruft die `IID_ISinkInterface` Schnittstelle.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="afxconnectionadvise"></a>  AfxConnectionAdvise  
 Mit dieser Funktion werden zum Herstellen einer Verbindung zwischen einer Quelle, angegeben durch `pUnkSrc`, und eine Ereignissenke, gemäß `pUnkSink`.  
  
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
 Der Schnittstellen-ID der Verbindung.  
  
 `bRefCount`  
 **"True"** gibt an, dass das Herstellen der Verbindung den Verweiszähler des verursachen `pUnkSink` vorwärts verschoben werden soll. **"False"** gibt an, dass der Verweiszähler nicht erhöht werden soll.  
  
 `pdwCookie`  
 Ein Zeiger auf eine `DWORD` , in denen ein Bezeichner der Verbindung zurückgegeben. Dieser Wert sollte übergeben werden, als die `dwCookie` Parameter `AfxConnectionUnadvise` beim Trennen der Verbindungs.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn eine Verbindung hergestellt wurde; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCConnectionPoints#8](../../mfc/codesnippet/cpp/connection-maps_3.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxctl.h 

##  <a name="afxconnectionunadvise"></a>  AfxConnectionUnadvise  
 Mit dieser Funktion können Sie eine Verbindung zwischen einer Quelle, angegeben durch Trennen `pUnkSrc`, und eine Ereignissenke, gemäß `pUnkSink`.  
  
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
 Die Schnittstellen-ID der Verbindungspunkt-Schnittstelle.  
  
 `bRefCount`  
 **"True"** gibt an, dass die Verbindung getrennt wird, den Verweiszähler des auftreten soll `pUnkSink` dekrementiert werden soll. **"False"** gibt an, dass der Verweiszähler nicht verringert werden soll.  
  
 `dwCookie`  
 Der Verbindungsbezeichner zurückgegebenes `AfxConnectionAdvise`.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn eine Verbindung getrennt wurde; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCConnectionPoints#9](../../mfc/codesnippet/cpp/connection-maps_4.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxctl.h 

## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
