---
title: Verbindungspunkt globale Funktionen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], global functions
ms.assetid: bcb4bf50-2155-4e20-b8bb-f2908b03a6e7
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 8271f512141e4d2cc274d180b31e1ad33bfc354e
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="connection-point-global-functions"></a>Verbindungspunkt globale Funktionen
Diese Funktionen bieten Unterstützung für Verbindungspunkte und Senke zugeordnet.  
  
> [!IMPORTANT]
>  In der folgenden Tabelle aufgeführten Funktionen können nicht verwendet werden, in Anwendungen, die in Ausführen der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlAdvise](#atladvise)|Erstellt eine Verbindung zwischen dem Verbindungspunkt eines Objekts und der Senke eines Clients.|  
|[AtlUnadvise](#atlunadvise)|Beendet die Verbindung mit `AtlAdvise`.|  
|[AtlAdviseSinkMap](#atladvisesinkmap)|Member- oder unadvises Einträge in eine Ereignissenke.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
   
##  <a name="atladvise"></a>AtlAdvise  
 Erstellt eine Verbindung zwischen dem Verbindungspunkt eines Objekts und der Senke eines Clients.  
  
> [!IMPORTANT]
>  Diese Funktion kann nicht verwendet werden, in Anwendungen, die in Ausführen der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
```
HRESULT    AtlAdvise(
    IUnknown* pUnkCP,
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw);
```  
  
### <a name="parameters"></a>Parameter  
 `pUnkCP`  
 [in] Ein Zeiger auf die **IUnknown** des Objekts der Client eine Verbindung mit herstellen möchte.  
  
 *pUnk*  
 [in] Ein Zeiger auf des Clients **IUnknown**.  
  
 `iid`  
 [in] Die GUID des Verbindungspunkts. In der Regel ist dies die von den Verbindungspunkt verwalteten Ausgangsschnittstelle identisch.  
  
 `pdw`  
 [out] Ein Zeiger auf das Cookie, das die Verbindung eindeutig identifiziert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Senke implementiert die ausgehende Schnittstelle vom Verbindungspunkt unterstützt. Der Client verwendet die `pdw` Cookies, um die Verbindung zu entfernen, durch Übergabe an [AtlUnadvise](#atlunadvise).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#91;](../../atl/codesnippet/cpp/connection-point-global-functions_1.cpp)]  
  
##  <a name="atlunadvise"></a>AtlUnadvise  
 Beendet die Verbindung mit [AtlAdvise](#atladvise).  
  
> [!IMPORTANT]
>  Diese Funktion kann nicht verwendet werden, in Anwendungen, die in Ausführen der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
```
HRESULT    AtlUnadvise(
    IUnknown* pUnkCP,
    const IID& iid,
    DWORD dw);
```  
  
### <a name="parameters"></a>Parameter  
 `pUnkCP`  
 [in] Ein Zeiger auf die **IUnknown** des Objekts, das der Client mit verbunden ist.  
  
 `iid`  
 [in] Die GUID des Verbindungspunkts. In der Regel ist dies die von den Verbindungspunkt verwalteten Ausgangsschnittstelle identisch.  
  
 `dw`  
 [in] Das Cookie, das die Verbindung eindeutig identifiziert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#96;](../../atl/codesnippet/cpp/connection-point-global-functions_2.cpp)]  
  
##  <a name="atladvisesinkmap"></a>AtlAdviseSinkMap  
 Mit dieser Funktion melden Sie alle Einträge in der Senkereigniszuordnung des Objekts an oder ab.  
  
> [!IMPORTANT]
>  Diese Funktion kann nicht verwendet werden, in Anwendungen, die in Ausführen der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
```
HRESULT AtlAdviseSinkMap(T* pT, bool bAdvise);
```  
  
### <a name="parameters"></a>Parameter  
 *pT*  
 [in] Ein Zeiger auf das Objekt, das die Sink-Zuordnung enthält.  
  
 `bAdvise`  
 [in] **true** Wenn alle Senke Einträge darüber informiert zu werden; **false** Wenn alle Senke Einträge unadvised werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#92;](../../atl/codesnippet/cpp/connection-point-global-functions_3.h)]  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)   
 [Connection Point-Makros](../../atl/reference/connection-point-macros.md)

