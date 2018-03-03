---
title: CCmdUI-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCmdUI
- AFXWIN/CCmdUI
- AFXWIN/CCmdUI::ContinueRouting
- AFXWIN/CCmdUI::Enable
- AFXWIN/CCmdUI::SetCheck
- AFXWIN/CCmdUI::SetRadio
- AFXWIN/CCmdUI::SetText
- AFXWIN/CCmdUI::m_nID
- AFXWIN/CCmdUI::m_nIndex
- AFXWIN/CCmdUI::m_pMenu
- AFXWIN/CCmdUI::m_pOther
- AFXWIN/CCmdUI::m_pSubMenu
dev_langs:
- C++
helpviewer_keywords:
- CCmdUI [MFC], ContinueRouting
- CCmdUI [MFC], Enable
- CCmdUI [MFC], SetCheck
- CCmdUI [MFC], SetRadio
- CCmdUI [MFC], SetText
- CCmdUI [MFC], m_nID
- CCmdUI [MFC], m_nIndex
- CCmdUI [MFC], m_pMenu
- CCmdUI [MFC], m_pOther
- CCmdUI [MFC], m_pSubMenu
ms.assetid: 04eaaaf5-f510-48ab-b425-94665ba24766
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 32413fe7939b5e5d5d3d41bf32a923dd308f0395
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccmdui-class"></a>CCmdUI-Klasse
Wird verwendet, nur innerhalb einer `ON_UPDATE_COMMAND_UI` Ereignishandler in einer `CCmdTarget`-abgeleitete Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CCmdUI  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCmdUI::ContinueRouting](#continuerouting)|Weist den Mechanismus Befehlsrouting Weiterleiten der aktuellen Nachricht unten die Kette der Handler fortgesetzt.|  
|[CCmdUI:: Enable auf](#enable)|Aktiviert oder deaktiviert das Element der Benutzeroberfläche für diesen Befehl.|  
|[CCmdUI::SetCheck](#setcheck)|Legt den Aktivierungszustand des Benutzeroberflächen-Elements für diesen Befehl an.|  
|[CCmdUI::SetRadio](#setradio)|Wie die `SetCheck` Memberfunktion ist, arbeitet aber Radio Gruppen.|  
|[CCmdUI::SetText](#settext)|Legt den Text für das Element der Benutzeroberfläche für diesen Befehl fest.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCmdUI::m_nID](#m_nid)|Die ID des Benutzeroberflächen-Objekts.|  
|[CCmdUI::m_nIndex](#m_nindex)|Der Index des Benutzeroberflächen-Objekts.|  
|[CCmdUI::m_pMenu](#m_pmenu)|Verweist auf das Menü, dargestellt durch die `CCmdUI` Objekt.|  
|[CCmdUI::m_pOther](#m_pother)|Verweist auf das Fensterobjekt, das die Benachrichtigung gesendet.|  
|[CCmdUI::m_pSubMenu](#m_psubmenu)|Verweist auf den darin enthaltenen Untermenüs dargestellt durch die `CCmdUI` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CCmdUI`eine Basisklasse verfügt nicht über.  
  
 Wenn ein Benutzer der Anwendung herunterlädt ein Menü, jede Menü Element muss wissen, ob er als aktiviert angezeigt werden sollen oder deaktiviert. Das Ziel eines Menübefehls stellt diese Informationen durch die Implementierung einer `ON_UPDATE_COMMAND_UI` Handler. Verwenden Sie für jede von der Benutzeroberfläche Befehlsobjekten in Ihrer Anwendung des Eigenschaftenfensters zum Erstellen eines meldungszuordnung Eintrag und die Funktion die Prototypen für jeden Handler.  
  
 Wenn Sie im Menü abgerufen wird, wird das Framework sucht und ruft jede `ON_UPDATE_COMMAND_UI` Handler, jeden Handler aufruft `CCmdUI` -Elementfunktionen wie z. B. **aktivieren** und **überprüfen**, und klicken Sie dann das Framework entsprechend zeigt jedes Menüelements.  
  
 Ein Menüelement kann mit einer Steuerleiste-Schaltfläche oder eines anderen Benutzeroberfläche Befehlsobjekt ersetzt werden, ohne Ändern des Codes in der `ON_UPDATE_COMMAND_UI` Handler.  
  
 In der folgenden Tabelle werden die Auswirkungen zusammengefasst `CCmdUI`des Memberfunktionen haben auf verschiedene Elemente klicken Benutzeroberflächen-Befehl.  
  
|Benutzeroberflächen-Element|Aktivieren|SetCheck|SetRadio|SetText|  
|--------------------------|------------|--------------|--------------|-------------|  
|Menüelement|Aktiviert oder deaktiviert|Aktiviert oder deaktiviert|Hier wird überprüft, ob ein Punkt mit|Legt Element text|  
|Symbolleisten-Schaltfläche|Aktiviert oder deaktiviert|Auswählt, hebt die Auswahl, oder einen unbestimmten Zustand|Identisch mit `SetCheck`|(Nicht zutreffend)|  
|Statusleiste|Stellt Text ein- oder ausgeblendet|Legt Popup- oder einen normalen Rahmen|Identisch mit `SetCheck`|Legt Bereich text|  
|Schaltfläche "Normal" auf`CDialogBar`|Aktiviert oder deaktiviert|Aktiviert oder deaktiviert das Kontrollkästchen|Identisch mit `SetCheck`|Legt den Schaltflächentext|  
|Im normalen-Steuerelement`CDialogBar`|Aktiviert oder deaktiviert|(Nicht zutreffend)|(Nicht zutreffend)|Legt Fenstertext|  
  
 Weitere Informationen über die Verwendung dieser Klasse finden Sie unter [wie Aktualisieren von Benutzeroberflächenobjekten](../../mfc/how-to-update-user-interface-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CCmdUI`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="continuerouting"></a>CCmdUI::ContinueRouting  
 Rufen Sie diese Memberfunktion zum Teilen des Mechanismus Befehlsrouting Weiterleiten der aktuellen Nachricht unten die Kette der Handler fortgesetzt.  
  
```  
void ContinueRouting();
```  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine erweiterte Memberfunktion, die in Verbindung mit verwendet werden soll ein `ON_COMMAND_EX` Handler, der gibt **"false"**. Weitere Informationen finden Sie unter [technischen Hinweis 6](../../mfc/tn006-message-maps.md).  
  
##  <a name="enable"></a>CCmdUI:: Enable auf  
 Rufen Sie diese Memberfunktion zum Aktivieren oder deaktivieren das Element der Benutzeroberfläche für diesen Befehl.  
  
```  
virtual void Enable(BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bOn`  
 **"True"** So aktivieren Sie das Element **"false"** zu deaktivieren.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#46](../../mfc/codesnippet/cpp/ccmdui-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#47](../../mfc/codesnippet/cpp/ccmdui-class_2.cpp)]  
  
##  <a name="m_nid"></a>CCmdUI::m_nID  
 Die ID des Menüelements, Symbolleisten-Schaltfläche oder ein anderes Benutzeroberfläche Objekt dargestellte der `CCmdUI` Objekt.  
  
```  
UINT m_nID;  
```  
  
##  <a name="m_nindex"></a>CCmdUI::m_nIndex  
 Der Index des Menüelements, Symbolleisten-Schaltfläche oder ein anderes Benutzeroberfläche Objekt dargestellte der `CCmdUI` Objekt.  
  
```  
UINT m_nIndex;  
```  
  
##  <a name="m_pmenu"></a>CCmdUI::m_pMenu  
 Zeiger (der `CMenu` Typ) auf das Menü, dargestellt durch die `CCmdUI` Objekt.  
  
```  
CMenu* m_pMenu;  
```  
  
### <a name="remarks"></a>Hinweise  
 **NULL** , wenn das Element nicht um ein Menü ist.  
  
##  <a name="m_psubmenu"></a>CCmdUI::m_pSubMenu  
 Zeiger (der `CMenu` Typ) auf den darin enthaltenen Untermenüs dargestellt durch die `CCmdUI` Objekt.  
  
```  
CMenu* m_pSubMenu;  
```  
  
### <a name="remarks"></a>Hinweise  
 **NULL** , wenn das Element nicht um ein Menü ist. Wenn das Untermenü ein Popupfenster wird `m_nID` enthält die ID des ersten Elements im Popupmenü. Weitere Informationen finden Sie unter [technischen Hinweis 21](../../mfc/tn021-command-and-message-routing.md).  
  
##  <a name="m_pother"></a>CCmdUI::m_pOther  
 Zeiger (vom Typ `CWnd`) in das Fensterobjekt, z. B. ein Tool oder Status-Leiste, die die Benachrichtigung gesendet.  
  
```  
CWnd* m_pOther;  
```  
  
### <a name="remarks"></a>Hinweise  
 **NULL** ist das Element eines Menüs oder einer nicht - `CWnd` Objekt.  
  
##  <a name="setcheck"></a>CCmdUI::SetCheck  
 Rufen Sie diese Memberfunktion, um das Element der Benutzeroberfläche für diesen Befehl auf den entsprechenden Aktivierungszustand festzulegen.  
  
```  
virtual void SetCheck(int nCheck = 1);
```  
  
### <a name="parameters"></a>Parameter  
 `nCheck`  
 Gibt den Aktivierungszustand festlegen. Wenn 0, deaktiviert; Wenn 1, überprüft. Wenn 2 wird unbestimmt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion funktioniert für Menüelemente und Symbolleisten-Schaltflächen. Unbestimmte Zustand gilt nur für Schaltflächen der Symbolleiste.  
  
##  <a name="setradio"></a>CCmdUI::SetRadio  
 Rufen Sie diese Memberfunktion, um das Element der Benutzeroberfläche für diesen Befehl auf den entsprechenden Aktivierungszustand festzulegen.  
  
```  
virtual void SetRadio(BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bOn`  
 **"True"** So aktivieren Sie das Element; andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion funktioniert wie `SetCheck`, außer dass er auf Elementen der Benutzeroberfläche, die als Teil einer Gruppe von Optionsfeld fungieren verwendet wird. Deaktivieren die anderen Elemente in der Gruppe erfolgt nicht automatisch, es sei denn, die Elemente selbst das Optionsfeld-Group-Verhalten beibehalten.  
  
##  <a name="settext"></a>CCmdUI::SetText  
 Rufen Sie diese Memberfunktion um den Text des Benutzeroberflächen-Elements für diesen Befehl festzulegen.  
  
```  
virtual void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszText`  
 Ein Zeiger auf eine Textzeichenfolge.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#48](../../mfc/codesnippet/cpp/ccmdui-class_3.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MDI](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)
