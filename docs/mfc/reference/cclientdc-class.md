---
title: CClientDC-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CClientDC
- AFXWIN/CClientDC
- AFXWIN/CClientDC::CClientDC
- AFXWIN/CClientDC::m_hWnd
dev_langs:
- C++
helpviewer_keywords:
- CClientDC [MFC], CClientDC
- CClientDC [MFC], m_hWnd
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a92fb471ee30e725cd97bff6cbda8d551c0bc859
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cclientdc-class"></a>CClientDC-Klasse
Übernimmt die Windows-Funktionen aufrufen [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871) bei der Konstruktion und [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920) zur zerstörungszeit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CClientDC : public CDC  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CClientDC::CClientDC](#cclientdc)|Erstellt eine `CClientDC` Objekt verbunden werden, um die `CWnd`.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CClientDC::m_hWnd](#m_hwnd)|Die `HWND` des Fensters auf die sich diese `CClientDC` gültig ist.|  
  
## <a name="remarks"></a>Hinweise  
 Dies bedeutet, dass den Gerätekontext zugeordneten ein `CClientDC` Objekt ist, das den Clientbereich eines Fensters.  
  
 Weitere Informationen zu `CClientDC`, finden Sie unter [Gerätekontexte](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CClientDC`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="cclientdc"></a>CClientDC::CClientDC  
 Erstellt eine `CClientDC` -Objekt, das den Clientbereich des greift auf die [CWnd](../../mfc/reference/cwnd-class.md) verweist `pWnd`.  
  
```  
explicit CClientDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Das Fenster, dessen Clientbereich der Gerätekontextobjekt zugegriffen wird.  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor ruft die Windows-Funktion [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871).  
  
 Eine Ausnahme (vom Typ `CResourceException`) wird ausgelöst, wenn die Windows `GetDC` -Aufruf fehl. Ein Gerätekontext möglicherweise nicht verfügbar, wenn Windows bereits alle verfügbaren Geräte Kontexten zugeordnet sind. Ihre Anwendung konkurriert für die fünf allgemeine Anzeige Kontexte zu einem beliebigen Zeitpunkt unter Windows verfügbar.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#42](../../mfc/codesnippet/cpp/cclientdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>CClientDC::m_hWnd  
 Die `HWND` von der `CWnd` Zeiger, die zum Erstellen der `CClientDC` Objekt.  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>Hinweise  
 `m_hWnd`ist eine geschützte Variable.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CClientDC::CClientDC](#cclientdc).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MDI](../../visual-cpp-samples.md)   
 [CDC-Klasse](../../mfc/reference/cdc-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDC-Klasse](../../mfc/reference/cdc-class.md)
