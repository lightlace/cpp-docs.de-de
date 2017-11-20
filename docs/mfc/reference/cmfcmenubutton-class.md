---
title: CMFCMenuButton-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CMFCMenuButton [MFC], CMFCMenuButton
- CMFCMenuButton [MFC], PreTranslateMessage
- CMFCMenuButton [MFC], SizeToContent
- CMFCMenuButton [MFC], m_bOSMenu
- CMFCMenuButton [MFC], m_bRightArrow
- CMFCMenuButton [MFC], m_bStayPressed
- CMFCMenuButton [MFC], m_hMenu
- CMFCMenuButton [MFC], m_nMenuResult
ms.assetid: 53d3d459-1e5a-47c5-8b7f-2e61f6af5187
caps.latest.revision: "32"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 43772dff0e09b7160c1ec28a6c62d341c124892e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
|[CMFCMenuButton::PreTranslateMessage](#pretranslatemessage)|Wird aufgerufen, durch das Framework um fenstermeldungen zu übersetzen, bevor sie verteilt wurden. (Überschreibt `CMFCButton::PreTranslateMessage`.)|  
|[CMFCMenuButton::SizeToContent](#sizetocontent)|Ändert die Größe der Schaltfläche entsprechend der Größe von Text- und Bilddateien.|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCMenuButton::m_bOSMenu](#m_bosmenu)|Gibt an, ob die Standard-System-Popupmenü angezeigt oder verwendet [CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu).|  
|[CMFCMenuButton::m_bRightArrow](#m_brightarrow)|Gibt an, ob das Menü das Popupmenü unterhalb oder rechts neben der Schaltfläche angezeigt wird.|  
|[CMFCMenuButton::m_bStayPressed](#m_bstaypressed)|Gibt an, ob die Menüschaltfläche seinen Zustand ändert, nachdem der Benutzer die loslässt.|  
|[CMFCMenuButton::m_hMenu](#m_hmenu)|Ein Handle für das angefügte Windows-Menü.|  
|[CMFCMenuButton::m_nMenuResult](#m_nmenuresult)|Ein Bezeichner, der gibt an, welches Element der Benutzer aus dem Popupmenü auswählen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCMenuButton` von abgeleitete Klasse die [CMFCButton Klasse](../../mfc/reference/cmfcbutton-class.md) die wiederum von abgeleitet ist, die [CButton Klasse](../../mfc/reference/cbutton-class.md). Aus diesem Grund können Sie `CMFCMenuButton` im Code die gleiche Weise Sie verwenden `CButton`.  
  
 Beim Erstellen einer `CMFCMenuButton`, müssen Sie ein Handle auf das zugeordnete Popupmenü übergeben. Rufen Sie die Funktion als Nächstes `CMFCMenuButton::SizeToContent`. `CMFCMenuButton::SizeToContent`überprüft, ob die Größe der Schaltfläche ist ausreichend, um einen Pfeil enthalten, der auf den Speicherort zeigt, wo das Popupfenster angezeigt – nämlich, unterhalb oder rechts neben der Schaltfläche wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie das Handle des Menüs auf die Schaltfläche "" angefügt, Größe der Schaltfläche der Größe von Text- und Bilddateien entsprechend anzupassen, und Festlegen der Popup-Menüs, das durch das Framework angezeigt wird. Dieser Codeausschnitt ist Teil der [neues Steuerelement-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#38](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#39](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
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
 Ein booleschen Member-Variable, welche Popupmenüs angibt, zeigt das Framework.  
  
```  
BOOL m_bOSMenu;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `m_bOSMenu` ist `TRUE`, das Framework Ruft die geerbte `TrackPopupMenu` -Standardmethode für dieses Objekt. Andernfalls das Framework ruft [CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu).  
  
##  <a name="m_brightarrow"></a>CMFCMenuButton::m_bRightArrow  
 Eine boolesche Membervariable, die den Speicherort des Popupmenüs angibt.  
  
```  
BOOL m_bRightArrow;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer die Schaltfläche drückt, zeigt die Anwendung ein Popupmenü an. Das Framework wird das Popup-Menü unter der Schaltfläche oder rechts neben der Schaltfläche angezeigt. Die Schaltfläche verfügt auch über einen kleinen Pfeil, der angibt, wo das Menü das Popupmenü angezeigt wird. Wenn `m_bRightArrow` ist `TRUE`, vom Framework das Menü das Popupmenü rechts neben der Schaltfläche angezeigt. Andernfalls wird unter der Schaltfläche im Popupmenü angezeigt.  
  
##  <a name="m_bstaypressed"></a>CMFCMenuButton::m_bStayPressed  
 Eine boolesche Membervariable, die angibt, ob die Menüschaltfläche angezeigt wird gedrückt, während der Benutzer eine Auswahl aus dem Popupmenü vornimmt.  
  
```  
BOOL m_bStayPressed;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `m_bStayPressed` angehört `FALSE`, die Menüschaltfläche wird nicht gedrückt werden, wenn verwendet, auf die Schaltfläche klickt. In diesem Fall zeigt das Framework nur im Popupmenü.  
  
 Wenn die `m_bStayPressed` angehört `TRUE`, die Menüschaltfläche wird gedrückt, wenn der Benutzer die Schaltfläche klickt. Nachdem der Benutzer das Menü das Popupmenü, entweder durch eine Auswahl treffen oder das Abbrechen der schließt bleibt bis gedrückten.  
  
##  <a name="m_hmenu"></a>CMFCMenuButton::m_hMenu  
 Das Handle für das angefügte Menü.  
  
```  
HMENU m_hMenu;  
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework zeigt das Menü, das durch diese Membervariable angegeben wird, wenn der Benutzer die Schaltfläche klickt.  
  
##  <a name="m_nmenuresult"></a>CMFCMenuButton::m_nMenuResult  
 Eine ganze Zahl, die gibt an, welches Element wählt der Benutzer aus dem Popupmenü.  
  
```  
int m_nMenuResult;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Wert dieser Variablen Member ist 0 (null), wenn der Benutzer über das Menü abbricht, ohne eine Auswahl getroffen, oder wenn ein Fehler auftritt.  
  
##  <a name="pretranslatemessage"></a>CMFCMenuButton::PreTranslateMessage  
 Wird aufgerufen, durch das Framework um fenstermeldungen zu übersetzen, bevor sie verteilt wurden.  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMsg`  
 Verweist auf eine [MSG](../../mfc/reference/msg-structure1.md) Struktur, die die zu verarbeitende Meldung enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Nachricht übersetzt wurde und nicht weitergeleitet werden soll; 0, wenn die Nachricht nicht übersetzt wurde und weitergeleitet werden soll.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="sizetocontent"></a>CMFCMenuButton::SizeToContent  
 Ändert die Größe der Schaltfläche entsprechend die Textgröße und Bildgröße.  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bCalcOnly`  
 Ein boolescher Parameter, der angibt, ob diese Methode ändert die Größe der Schaltfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt, das die neue Größe für die Schaltfläche angibt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie diese Funktion aufrufen und `bCalcOnly` ist `TRUE`, `SizeToContent` wird nur die neue Größe der Schaltfläche zu berechnen.  
  
 Die neue Größe der Schaltfläche wird berechnet, an den Schaltflächentext, Bild und Pfeil anpassen. Das Framework fügt auch in vordefinierten Ränder 10 Pixel für die horizontale Kante und 5 Pixel für die vertikale Kante.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCButton-Klasse](../../mfc/reference/cmfcbutton-class.md)
