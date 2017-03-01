---
title: CCmdUI-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCmdUI
dev_langs:
- C++
helpviewer_keywords:
- user interfaces, updating
- states, updating user interface object
- updating user interfaces for commands
- commands [C++], updating UI
- CCmdUI class
- toolbars [C++], updating
- command user interface
- menus [C++], updating as context changes
- buttons [C++], updating as context changes
ms.assetid: 04eaaaf5-f510-48ab-b425-94665ba24766
caps.latest.revision: 21
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
ms.openlocfilehash: beb84a0f0f96c7a8acb5c432c7402b3e62b94518
ms.lasthandoff: 02/24/2017

---
# <a name="ccmdui-class"></a>CCmdUI-Klasse
Wird verwendet, nur innerhalb einer `ON_UPDATE_COMMAND_UI` Ereignishandler in einer `CCmdTarget`-abgeleitete Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CCmdUI  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCmdUI::ContinueRouting](#continuerouting)|Teilt Befehlsrouting Mechanismus für die Weiterleitung der aktuellen Nachricht der Vererbungskette Handler fortgesetzt.|  
|[CCmdUI:: Enable auf](#enable)|Aktiviert oder deaktiviert die Benutzeroberflächen-Element für diesen Befehl.|  
|[CCmdUI::SetCheck](#setcheck)|Legt den Aktivierungszustand des Elements Benutzeroberfläche für diesen Befehl fest.|  
|[CCmdUI::SetRadio](#setradio)|Wie die `SetCheck` Memberfunktion kann jedoch Radio Gruppen.|  
|[CCmdUI::SetText](#settext)|Legt den Text für das Element der Benutzeroberfläche für diesen Befehl.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCmdUI::m_nID](#m_nid)|Die ID des Benutzeroberflächen-Objekts.|  
|[CCmdUI::m_nIndex](#m_nindex)|Der Index des Benutzeroberflächen-Objekts.|  
|[CCmdUI::m_pMenu](#m_pmenu)|Verweist auf das Menü, dargestellt durch die `CCmdUI` Objekt.|  
|[CCmdUI::m_pOther](#m_pother)|Verweist auf das Window-Objekt, das die Benachrichtigung gesendet.|  
|[CCmdUI::m_pSubMenu](#m_psubmenu)|Verweist auf die enthaltenen Untermenü dargestellt durch die `CCmdUI` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CCmdUI`eine Basisklasse keinen.  
  
 Wenn ein Benutzer der Anwendung abgerufene ein Menü, jedes Menü-Element muss wissen, ob es angezeigt werden soll, als aktiviert oder deaktiviert. Das Ziel eines Menübefehls bietet diese Informationen durch die Implementierung einer `ON_UPDATE_COMMAND_UI` Handler. Verwenden Sie das Fenster Eigenschaften für jeden Befehl Benutzeroberflächen-Objekte in Ihrer Anwendung zum Erstellen eines meldungszuordnung Eintrag und die Funktion die Prototypen für jeden Handler.  
  
 Wenn das Menü abgerufen wird, wird das Framework sucht und ruft jede `ON_UPDATE_COMMAND_UI` -Handler, jeder Handler ruft `CCmdUI` Memberfunktionen wie z. B. **aktivieren** und **überprüfen**, und das Framework zeigt dann entsprechend jedes Menüelement.  
  
 Ein Menüelement kann durch eine Steuerleiste Schaltfläche oder ein anderes Objekt der Befehl Benutzeroberfläche ersetzt werden, ohne den Code innerhalb der `ON_UPDATE_COMMAND_UI` Handler.  
  
 In der folgenden Tabelle werden die Auswirkungen zusammengefasst `CCmdUI`die Memberfunktionen, die auf verschiedene Befehl Benutzeroberflächen-Elemente haben.  
  
|Benutzeroberflächen-Element|Aktivieren|SetCheck|SetRadio|SetText|  
|--------------------------|------------|--------------|--------------|-------------|  
|Menüelement|Aktiviert oder deaktiviert|(×) Aktiviert oder deaktiviert|Tests unter Verwendung der Punkt (•)|Legt Element text|  
|Symbolleisten-Schaltfläche|Aktiviert oder deaktiviert|Auswählt, hebt die Auswahl, oder einen unbestimmten Zustand|Identisch mit`SetCheck`|(Nicht zutreffend)|  
|Statusleiste|Wird der Text sichtbar oder unsichtbar|Legt in neuem Fenster öffnen oder ein normaler Rahmen|Identisch mit`SetCheck`|Wird im Bereich text|  
|Normale Schaltfläche`CDialogBar`|Aktiviert oder deaktiviert|Aktiviert oder deaktiviert das Kontrollkästchen|Identisch mit`SetCheck`|Legt den Schaltflächentext|  
|Im normalen-Steuerelement`CDialogBar`|Aktiviert oder deaktiviert|(Nicht zutreffend)|(Nicht zutreffend)|Text in Sätze|  
  
 Weitere Informationen über die Verwendung dieser Klasse finden Sie unter [wie Aktualisieren von Benutzeroberflächenobjekten](../../mfc/how-to-update-user-interface-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CCmdUI`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="a-namecontinueroutinga--ccmduicontinuerouting"></a><a name="continuerouting"></a>CCmdUI::ContinueRouting  
 Rufen Sie diese Memberfunktion zum Befehlsrouting Mechanismus für die Weiterleitung der aktuellen Nachricht der Vererbungskette Handler weiter zu informieren.  
  
```  
void ContinueRouting();
```  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine erweiterte Memberfunktion, die in Verbindung mit verwendet werden, sollte ein `ON_COMMAND_EX` Handler, der zurückgibt **FALSE**. Weitere Informationen finden Sie unter [Technische Hinweis 6](../../mfc/tn006-message-maps.md).  
  
##  <a name="a-nameenablea--ccmduienable"></a><a name="enable"></a>CCmdUI:: Enable auf  
 Rufen Sie diese Memberfunktion zum Aktivieren oder deaktivieren das Element der Benutzeroberfläche für diesen Befehl.  
  
```  
virtual void Enable(BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bOn`  
 **True,** aktivieren Sie das Element **FALSE** deaktivieren.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#46;](../../mfc/codesnippet/cpp/ccmdui-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#47;](../../mfc/codesnippet/cpp/ccmdui-class_2.cpp)]  
  
##  <a name="a-namemnida--ccmduimnid"></a><a name="m_nid"></a>CCmdUI::m_nID  
 Die ID des Menüelements, Symbolleisten-Schaltfläche oder ein anderes dargestellte Benutzeroberfläche-Objekt die `CCmdUI` Objekt.  
  
```  
UINT m_nID;  
```  
  
##  <a name="a-namemnindexa--ccmduimnindex"></a><a name="m_nindex"></a>CCmdUI::m_nIndex  
 Der Index des Menüelements, Symbolleisten-Schaltfläche oder ein anderes dargestellte Benutzeroberfläche-Objekt die `CCmdUI` Objekt.  
  
```  
UINT m_nIndex;  
```  
  
##  <a name="a-namempmenua--ccmduimpmenu"></a><a name="m_pmenu"></a>CCmdUI::m_pMenu  
 Zeiger (der `CMenu` Typ) auf das Menü, dargestellt durch die `CCmdUI` Objekt.  
  
```  
CMenu* m_pMenu;  
```  
  
### <a name="remarks"></a>Hinweise  
 **NULL** , wenn das Element ein Menü nicht ist.  
  
##  <a name="a-namempsubmenua--ccmduimpsubmenu"></a><a name="m_psubmenu"></a>CCmdUI::m_pSubMenu  
 Zeiger (der `CMenu` Typ) dargestellte enthaltenen Untermenü zu den `CCmdUI` Objekt.  
  
```  
CMenu* m_pSubMenu;  
```  
  
### <a name="remarks"></a>Hinweise  
 **NULL** , wenn das Element ein Menü nicht ist. Wenn das Untermenü ein Popup ist `m_nID` enthält die ID des ersten Elements im Popup-Menü. Weitere Informationen finden Sie unter [Technische Hinweis 21](../../mfc/tn021-command-and-message-routing.md).  
  
##  <a name="a-namempothera--ccmduimpother"></a><a name="m_pother"></a>CCmdUI::m_pOther  
 Zeiger (vom Typ `CWnd`) auf der Window-Objekt, z. B. eine Leiste Tool oder Status, die die Benachrichtigung gesendet.  
  
```  
CWnd* m_pOther;  
```  
  
### <a name="remarks"></a>Hinweise  
 **NULL** ist das Element ein Menü oder ein nicht- `CWnd` Objekt.  
  
##  <a name="a-namesetchecka--ccmduisetcheck"></a><a name="setcheck"></a>CCmdUI::SetCheck  
 Rufen Sie diese Memberfunktion, um das Element der Benutzeroberfläche für diesen Befehl auf den entsprechenden Aktivierungszustand festgelegt.  
  
```  
virtual void SetCheck(int nCheck = 1);
```  
  
### <a name="parameters"></a>Parameter  
 `nCheck`  
 Gibt den Aktivierungszustand festgelegt. Wenn 0, deaktiviert; Wenn 1, überprüft. und bei 2 unbestimmt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion funktioniert für Menüelemente und Symbolleisten-Schaltflächen. Unbestimmte Zustand gilt nur für Schaltflächen der Symbolleiste.  
  
##  <a name="a-namesetradioa--ccmduisetradio"></a><a name="setradio"></a>CCmdUI::SetRadio  
 Rufen Sie diese Memberfunktion, um das Element der Benutzeroberfläche für diesen Befehl auf den entsprechenden Aktivierungszustand festgelegt.  
  
```  
virtual void SetRadio(BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bOn`  
 **True,** aktivieren Sie das Element; andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion funktioniert ähnlich wie `SetCheck`, außer dass es Elementen der Benutzeroberfläche, die als Teil einer Gruppe von Optionsfeldern verarbeitet. Deaktivieren die anderen Elemente in der Gruppe erfolgt nicht automatisch, es sei denn, die Elemente selbst das Verhalten des Sender-Gruppe verwalten.  
  
##  <a name="a-namesettexta--ccmduisettext"></a><a name="settext"></a>CCmdUI::SetText  
 Rufen Sie diese Memberfunktion zum Text der Benutzeroberflächen-Element für diesen Befehl festgelegt werden.  
  
```  
virtual void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszText`  
 Ein Zeiger auf eine Textzeichenfolge.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#48;](../../mfc/codesnippet/cpp/ccmdui-class_3.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MDI](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)

