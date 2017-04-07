---
title: Klasse CMFCMenuButton | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::PreTranslateMessage
- AFXMENUBUTTON/CMFCMenuButton::SizeToContent
- AFXMENUBUTTON/CMFCMenuButton::m_bOSMenu
- AFXMENUBUTTON/CMFCMenuButton::m_bRightArrow
- AFXMENUBUTTON/CMFCMenuButton::m_bStayPressed
- AFXMENUBUTTON/CMFCMenuButton::m_hMenu
- AFXMENUBUTTON/CMFCMenuButton::m_nMenuResult
dev_langs:
- C++
helpviewer_keywords:
- CMFCMenuButton class
ms.assetid: 53d3d459-1e5a-47c5-8b7f-2e61f6af5187
caps.latest.revision: 32
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 65c334ce68dbbbae2b21da2c40aa9420cdeb51bd
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcmenubutton-class"></a>CMFCMenuButton-Klasse
Eine Schaltfläche, die ein Popupmenü anzeigt und die vom Benutzer gewählte Menüoption meldet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCMenuButton : public CMFCButton  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCMenuButton::CMFCMenuButton](#cmfcmenubutton)|Erstellt ein `CMFCMenuButton`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCMenuButton::PreTranslateMessage](#pretranslatemessage)|Aufgerufen, um fenstermeldungen zu übersetzen, bevor sie verteilt wurden. (Überschreibt `CMFCButton::PreTranslateMessage`.)|  
|[CMFCMenuButton::SizeToContent](#sizetocontent)|Ändert die Größe der Schaltfläche entsprechend der Größe von Text- und Bilddaten.|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCMenuButton::m_bOSMenu](#m_bosmenu)|Gibt an, ob die Standard-System-Popupmenü anzuzeigen oder [CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu).|  
|[CMFCMenuButton::m_bRightArrow](#m_brightarrow)|Gibt an, ob das Popupmenü unterhalb oder rechts neben der Schaltfläche angezeigt wird.|  
|[CMFCMenuButton::m_bStayPressed](#m_bstaypressed)|Gibt an, ob die Schaltfläche dessen Zustand ändert, nachdem der Benutzer die Schaltfläche freigibt.|  
|[CMFCMenuButton::m_hMenu](#m_hmenu)|Ein Handle für das angefügte Menü von Windows.|  
|[CMFCMenuButton::m_nMenuResult](#m_nmenuresult)|Ein Bezeichner, der gibt an, welches Element der Benutzer aus dem Popupmenü auswählen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCMenuButton` von abgeleitete Klasse der [CMFCButton Klasse](../../mfc/reference/cmfcbutton-class.md) die wiederum von abgeleitet ist, die [CButton Klasse](../../mfc/reference/cbutton-class.md). Daher können Sie `CMFCMenuButton` in Ihrem Code die gleiche Weise Sie verwenden `CButton`.  
  
 Beim Erstellen einer `CMFCMenuButton`, müssen Sie ein Handle an die zugeordnete Popupmenü übergeben. Als Nächstes rufen Sie die Funktion `CMFCMenuButton::SizeToContent`. `CMFCMenuButton::SizeToContent`überprüft, ob die Größe der Schaltfläche ist ausreichend, um einen Pfeil enthalten, der auf den Speicherort zeigt, wo das Popup-Fenster - nämlich unter oder rechts neben der Schaltfläche angezeigt wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie das Handle des Menüs an die Schaltfläche angefügten festzulegen, ändern Sie die Größe der Schaltfläche entsprechend der Größe von Text und Bild und legen Sie im Popupmenü, die vom Framework angezeigt wird. Dieser Codeausschnitt ist Teil der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#38;](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls Nr.&39;](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxmenubutton.h  
  
##  <a name="cmfcmenubutton"></a>CMFCMenuButton::CMFCMenuButton  
 Erstellt ein neues [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md) Objekt.  
  
```  
CMFCMenuButton();
```  
  
##  <a name="m_bosmenu"></a>CMFCMenuButton::m_bOSMenu  
 Ein booleschen Member-Variable, die Popup-Menü angibt, zeigt das Framework.  
  
```  
BOOL m_bOSMenu;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `m_bOSMenu` ist `TRUE`, ruft das Framework die geerbte `TrackPopupMenu` Methode für dieses Objekt. Andernfalls ruft das Framework [CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu).  
  
##  <a name="m_brightarrow"></a>CMFCMenuButton::m_bRightArrow  
 Eine boolesche Membervariable, die die Position des Popupmenüs angibt.  
  
```  
BOOL m_bRightArrow;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer die Schaltfläche klickt, zeigt die Anwendung ein Popup-Menü. Das Framework wird das Popup-Menü unter der Schaltfläche oder rechts neben der Schaltfläche angezeigt. Die Schaltfläche verfügt auch über einen kleinen Pfeil, der angibt, in dem das Kontextmenü angezeigt wird. Wenn `m_bRightArrow` ist `TRUE`, vom Framework das Popupmenü rechts neben der Schaltfläche angezeigt. Andernfalls wird das Popup-Menü unter der Schaltfläche angezeigt.  
  
##  <a name="m_bstaypressed"></a>CMFCMenuButton::m_bStayPressed  
 Eine boolesche Membervariable, die angibt, ob die Schaltfläche angezeigt wird gedrückt, während der Benutzer eine Auswahl aus dem Popupmenü trifft.  
  
```  
BOOL m_bStayPressed;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `m_bStayPressed` gehört `FALSE`, die Schaltfläche ist nicht gedrückt werden, wenn verwendet, auf die Schaltfläche klickt. In diesem Fall zeigt das Framework nur das Popup-Menü.  
  
 Wenn die `m_bStayPressed` gehört `TRUE`, die Schaltfläche wird gedrückt, wenn der Benutzer auf die Schaltfläche klickt. Nachdem der Benutzer die Popup-Menü, indem Sie eine Auswahl treffen oder stornieren schließt bleibt bis gedrückt.  
  
##  <a name="m_hmenu"></a>CMFCMenuButton::m_hMenu  
 Das Handle für das angefügte Menü.  
  
```  
HMENU m_hMenu;  
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework zeigt das Menü, das durch diese Membervariable angegeben werden, wenn der Benutzer auf die Schaltfläche klickt.  
  
##  <a name="m_nmenuresult"></a>CMFCMenuButton::m_nMenuResult  
 Eine ganze Zahl, die gibt an, welches Element wählt der Benutzer aus dem Popupmenü.  
  
```  
int m_nMenuResult;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Wert dieser Membervariablen ist&0; (null), wenn der Benutzer im Menü abbricht, ohne eine Auswahl zu treffen, oder wenn ein Fehler auftritt.  
  
##  <a name="pretranslatemessage"></a>CMFCMenuButton::PreTranslateMessage  
 Aufgerufen, um fenstermeldungen zu übersetzen, bevor sie verteilt wurden.  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMsg`  
 Verweist auf eine [MSG](../../mfc/reference/msg-structure1.md) Struktur, die die zu verarbeitende Meldung enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Meldung übersetzt wurde und nicht weitergeleitet werden soll; 0, wenn die Nachricht nicht übersetzt wurde und weitergeleitet werden soll.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="sizetocontent"></a>CMFCMenuButton::SizeToContent  
 Ändert die Größe der Schaltfläche entsprechend seiner Text und Imagegröße.  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bCalcOnly`  
 Ein boolescher Parameter, der angibt, ob es sich bei dieser Methode wird die Größe der Schaltfläche geändert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt, das die neue Größe für die Schaltfläche angibt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie diese Funktion aufrufen und `bCalcOnly` ist `TRUE`, `SizeToContent` berechnet nur die neue Größe der Schaltfläche.  
  
 Die neue Größe der Schaltfläche wird an die Schaltflächentext, Bild und Pfeil berechnet. Das Framework fügt auch vordefinierte Rand von 10 Pixel für die horizontale Kante und 5 Pixel für die vertikale Kante.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCButton-Klasse](../../mfc/reference/cmfcbutton-class.md)

