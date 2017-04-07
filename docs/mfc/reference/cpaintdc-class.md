---
title: CPaintDC-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPaintDC
- AFXWIN/CPaintDC
- AFXWIN/CPaintDC::CPaintDC
- AFXWIN/CPaintDC::m_ps
- AFXWIN/CPaintDC::m_hWnd
dev_langs:
- C++
helpviewer_keywords:
- OnPaint handler
- WM_PAINT message
- CPaintDC class
ms.assetid: 7e245baa-bf9b-403e-a637-7218adf28fab
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
ms.openlocfilehash: b781db7d4a6676e6fc6ad5df7553b9c9a0154ab9
ms.lasthandoff: 02/24/2017

---
# <a name="cpaintdc-class"></a>CPaintDC-Klasse
Eine Gerätekontext abgeleitete Klasse [CDC](../../mfc/reference/cdc-class.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPaintDC : public CDC  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPaintDC::CPaintDC](#cpaintdc)|Erstellt eine `CPaintDC` verbunden mit dem angegebenen [CWnd](../../mfc/reference/cwnd-class.md).|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPaintDC::m_ps](#m_ps)|Enthält die [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) verwendet, um den Clientbereich zu zeichnen.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPaintDC::m_hWnd](#m_hwnd)|Die `HWND` an das `CPaintDC` Objekt angefügt ist.|  
  
## <a name="remarks"></a>Hinweise  
 Er führt eine [CWnd::BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint) zur Konstruktionszeit und [CWnd::EndPaint](../../mfc/reference/cwnd-class.md#endpaint) der Zerstörung.  
  
 Ein `CPaintDC` Objekt kann nur verwendet werden, bei der Reaktion auf einen [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) Meldung, in der Regel in Ihrem `OnPaint` Meldungshandler-Memberfunktion.  
  
 Weitere Informationen zur Verwendung von `CPaintDC`, finden Sie unter [Gerätekontexte](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CPaintDC`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="cpaintdc"></a>CPaintDC::CPaintDC  
 Erstellt eine `CPaintDC` -Objekt, das Anwendungsfenster zeichnen vorbereitet und speichert die [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) -Struktur der [M_ps](#m_ps) Membervariable.  
  
```  
explicit CPaintDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Verweist auf die `CWnd` -Objekt, dem die `CPaintDC` Objekt gehört.  
  
### <a name="remarks"></a>Hinweise  
 Eine Ausnahme (vom Typ `CResourceException`) ausgelöst, wenn die Windows [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871) -Aufruf fehl. Ein Gerätekontext möglicherweise nicht verfügbar, wenn Windows bereits alle verfügbaren Geräte Kontexten zugeordnet sind. Ihre Anwendung konkurriert für die fünf allgemeine Anzeige Kontexte zu einem beliebigen Zeitpunkt unter Windows verfügbar.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#97;](../../mfc/codesnippet/cpp/cpaintdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>CPaintDC::m_hWnd  
 Die `HWND` an das `CPaintDC` Objekt angefügt ist.  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>Hinweise  
 `m_hWnd`eine geschützte Variable vom Typ `HWND`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#98;](../../mfc/codesnippet/cpp/cpaintdc-class_2.cpp)]  
  
##  <a name="m_ps"></a>CPaintDC::m_ps  
 `m_ps`ist eine öffentliche Member-Variable des Typs [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md).  
  
```  
PAINTSTRUCT m_ps;  
```  
  
### <a name="remarks"></a>Hinweise  
 Es ist die `PAINTSTRUCT` , übergeben und ausgefüllt [CWnd::BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint).  
  
 Die `PAINTSTRUCT` enthält Informationen, die die Anwendung, die zum Zeichnen des Clientbereichs des Fensters zugeordnet verwendet ein `CPaintDC` Objekt.  
  
 Beachten Sie, dass Sie, das Gerät Kontexthandle über zugreifen können die `PAINTSTRUCT`. Allerdings können Sie zugreifen, das Handle direkt über die `m_hDC` Membervariable, `CPaintDC` erbt von `CDC`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPaintDC::m_hWnd](#m_hwnd).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MDI](../../visual-cpp-samples.md)   
 [CDC-Klasse](../../mfc/reference/cdc-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




