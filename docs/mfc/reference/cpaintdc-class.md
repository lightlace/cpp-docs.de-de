---
title: CPaintDC-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CPaintDC [MFC], CPaintDC
- CPaintDC [MFC], m_ps
- CPaintDC [MFC], m_hWnd
ms.assetid: 7e245baa-bf9b-403e-a637-7218adf28fab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d9f83c36a9c1a0d334e3b4a75724521d5711123e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376534"
---
# <a name="cpaintdc-class"></a>CPaintDC-Klasse
Eine Gerätekontextklasse abgeleitet [CDC](../../mfc/reference/cdc-class.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPaintDC : public CDC  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPaintDC::CPaintDC](#cpaintdc)|Erstellt eine `CPaintDC` verbunden mit dem angegebenen [CWnd](../../mfc/reference/cwnd-class.md).|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPaintDC::m_ps](#m_ps)|Enthält die [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) verwendet, um den Clientbereich zu zeichnen.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CPaintDC::m_hWnd](#m_hwnd)|Die `HWND` an das `CPaintDC` Objekt angefügt ist.|  
  
## <a name="remarks"></a>Hinweise  
 Es führt eine [CWnd:: BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint) bei der Konstruktion und [CWnd::EndPaint](../../mfc/reference/cwnd-class.md#endpaint) zur zerstörungszeit.  
  
 Ein `CPaintDC` Objekt kann nur verwendet werden, bei der Reaktion auf eine [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) Meldung, in der Regel in Ihre `OnPaint` Nachrichtenhandler Memberfunktion.  
  
 Weitere Informationen zur Verwendung von `CPaintDC`, finden Sie unter [Gerätekontexte](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CPaintDC`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="cpaintdc"></a>  CPaintDC::CPaintDC  
 Erstellt eine `CPaintDC` -Objekt, das Anwendungsfenster für zeichnen vorbereitet und speichert die [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) Struktur der [M_ps](#m_ps) Membervariablen gespeichert.  
  
```  
explicit CPaintDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Verweist auf die `CWnd` Objekt, mit dem die `CPaintDC` Objekt gehört.  
  
### <a name="remarks"></a>Hinweise  
 Eine Ausnahme (vom Typ `CResourceException`) wird ausgelöst, wenn die Windows [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871) -Aufruf fehl. Ein Gerätekontext möglicherweise nicht verfügbar, wenn Windows bereits alle verfügbaren Geräte Kontexten zugeordnet sind. Ihre Anwendung konkurriert für die fünf allgemeine Anzeige Kontexte zu einem beliebigen Zeitpunkt unter Windows verfügbar.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#97](../../mfc/codesnippet/cpp/cpaintdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>  CPaintDC::m_hWnd  
 Die `HWND` an das `CPaintDC` Objekt angefügt ist.  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>Hinweise  
 `m_hWnd` eine geschützte Variable vom Typ `HWND`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#98](../../mfc/codesnippet/cpp/cpaintdc-class_2.cpp)]  
  
##  <a name="m_ps"></a>  CPaintDC::m_ps  
 `m_ps` wird eine Variablen öffentlichen Member des Typs [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md).  
  
```  
PAINTSTRUCT m_ps;  
```  
  
### <a name="remarks"></a>Hinweise  
 Es ist die `PAINTSTRUCT` , übergeben und von ausgefüllt [CWnd:: BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint).  
  
 Die `PAINTSTRUCT` enthält Informationen, die die Anwendung verwendet wird, das den Clientbereich des Fensters zugeordneten Paint-Ereignis ein `CPaintDC` Objekt.  
  
 Beachten Sie, dass Sie das Gerätekontext Handle über zugreifen, können die `PAINTSTRUCT`. Allerdings können Sie zugreifen, das Handle direkt über die `m_hDC` Membervariable, `CPaintDC` erbt von `CDC`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPaintDC::m_hWnd](#m_hwnd).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MDI](../../visual-cpp-samples.md)   
 [CDC-Klasse](../../mfc/reference/cdc-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



