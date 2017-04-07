---
title: CClientDC-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- CClientDC class
- device contexts, client area
- client-area device context
- CDC class, device contexts for client areas
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
caps.latest.revision: 22
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 619bed4d31994bde8464ad710e9f050d6ba0696a
ms.lasthandoff: 02/24/2017

---
# <a name="cclientdc-class"></a>CClientDC-Klasse
Übernimmt die Windows-Funktionen aufrufen [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871) zur Konstruktionszeit und [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920) der Zerstörung.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CClientDC : public CDC  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CClientDC::CClientDC](#cclientdc)|Erstellt eine `CClientDC` Objekt verbunden, um die `CWnd`.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CClientDC::m_hWnd](#m_hwnd)|Die `HWND` des Fensters für die diese `CClientDC` gültig ist.|  
  
## <a name="remarks"></a>Hinweise  
 Dies bedeutet, dass der Gerätekontext zugeordnet ein `CClientDC` Objekt ist, das den Clientbereich eines Fensters.  
  
 Weitere Informationen zu `CClientDC`, finden Sie unter [Gerätekontexte](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CClientDC`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="cclientdc"></a>CClientDC::CClientDC  
 Erstellt eine `CClientDC` -Objekt, das den Clientbereich des greift auf die [CWnd](../../mfc/reference/cwnd-class.md) auf den `pWnd`.  
  
```  
explicit CClientDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Das Fenster, dessen Clientbereich der Gerätekontextobjekt zugreifen.  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor ruft die Windows-Funktion [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871).  
  
 Eine Ausnahme (vom Typ `CResourceException`) ausgelöst, wenn die Windows `GetDC` -Aufruf fehl. Ein Gerätekontext möglicherweise nicht verfügbar, wenn Windows bereits alle verfügbaren Geräte Kontexten zugeordnet sind. Ihre Anwendung konkurriert für die fünf allgemeine Anzeige Kontexte zu einem beliebigen Zeitpunkt unter Windows verfügbar.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#42;](../../mfc/codesnippet/cpp/cclientdc-class_1.cpp)]  
  
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

