---
title: CStatusBar-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStatusBar
- AFXEXT/CStatusBar
- AFXEXT/CStatusBar::CStatusBar
- AFXEXT/CStatusBar::CommandToIndex
- AFXEXT/CStatusBar::Create
- AFXEXT/CStatusBar::CreateEx
- AFXEXT/CStatusBar::DrawItem
- AFXEXT/CStatusBar::GetItemID
- AFXEXT/CStatusBar::GetItemRect
- AFXEXT/CStatusBar::GetPaneInfo
- AFXEXT/CStatusBar::GetPaneStyle
- AFXEXT/CStatusBar::GetPaneText
- AFXEXT/CStatusBar::GetStatusBarCtrl
- AFXEXT/CStatusBar::SetIndicators
- AFXEXT/CStatusBar::SetPaneInfo
- AFXEXT/CStatusBar::SetPaneStyle
- AFXEXT/CStatusBar::SetPaneText
dev_langs:
- C++
helpviewer_keywords:
- CStatusBar [MFC], CStatusBar
- CStatusBar [MFC], CommandToIndex
- CStatusBar [MFC], Create
- CStatusBar [MFC], CreateEx
- CStatusBar [MFC], DrawItem
- CStatusBar [MFC], GetItemID
- CStatusBar [MFC], GetItemRect
- CStatusBar [MFC], GetPaneInfo
- CStatusBar [MFC], GetPaneStyle
- CStatusBar [MFC], GetPaneText
- CStatusBar [MFC], GetStatusBarCtrl
- CStatusBar [MFC], SetIndicators
- CStatusBar [MFC], SetPaneInfo
- CStatusBar [MFC], SetPaneStyle
- CStatusBar [MFC], SetPaneText
ms.assetid: a3bde3db-e71c-4881-a3ca-1d5481c345ba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb5fb6b09ba6d27828c9f76a1b2ee21323197f6b
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122940"
---
# <a name="cstatusbar-class"></a>CStatusBar-Klasse
Eine Steuerleiste mit einer Zeile von Textausgabebereichen ("Indikatoren" genannt).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CStatusBar : public CControlBar  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStatusBar::CStatusBar](#cstatusbar)|Erstellt ein `CStatusBar`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStatusBar::CommandToIndex](#commandtoindex)|Ruft Index für einen bestimmten Indikator-ID.|  
|[CStatusBar::Create](#create)|Die Statusleiste erstellt, fügt es der `CStatusBar` -Objekt und legt die anfängliche Höhe der Schriftart und Balken.|  
|[CStatusBar:: CreateEx](#createex)|Erstellt eine `CStatusBar` Objekt mit zusätzlichen Formatvorlagen für das eingebettete `CStatusBarCtrl` Objekt.|  
|[CStatusBar::DrawItem](#drawitem)|Wird aufgerufen, wenn sich ein Darstellungsaspekt eines ein ownerdrawn-Statusleisten-Steuerelements ändert.|  
|[CStatusBar::GetItemID](#getitemid)|Ruft den Indikator-ID für einen bestimmten Index ab.|  
|[CStatusBar::GetItemRect](#getitemrect)|Ruft anzeigen Rechteck für einen bestimmten Index.|  
|[CStatusBar::GetPaneInfo](#getpaneinfo)|Ruft Anzeige-ID,-Stil und -Breite für einen bestimmten Index.|  
|[CStatusBar::GetPaneStyle](#getpanestyle)|Ruft die indikatorart für einen bestimmten Index ab.|  
|[CStatusBar::GetPaneText](#getpanetext)|Ruft den Indikatortext für einen bestimmten Index ab.|  
|[GetStatusBarCtrl](#getstatusbarctrl)|Ermöglicht den direkten Zugriff auf die zugrunde liegenden Standardsteuerelements.|  
|[CStatusBar:: SetIndicators](#setindicators)|Legt die Symbol-IDs.|  
|[CStatusBar::SetPaneInfo](#setpaneinfo)|Indikator-ID, Stil und Breite für einen bestimmten Index festgelegt.|  
|[CStatusBar::SetPaneStyle](#setpanestyle)|Legt die indikatorart für einen bestimmten Index fest.|  
|[CStatusBar::SetPaneText](#setpanetext)|Legt Indikatortext für einen bestimmten Index fest.|  
  
## <a name="remarks"></a>Hinweise  
 Die Ausgabebereiche werden häufig als Nachricht Linien und als Statusindikatoren verwendet. Beispiele sind im Menü Hilfe-Nachricht Zeilen, die den ausgewählten Menübefehl kurz und die Indikatoren, die den Status von Rollen, NUM- und andere Schlüssel anzuzeigen.  
  
 [GetStatusBarCtrl](#getstatusbarctrl), eine Memberfunktion neue MFC 4.0, können Sie das allgemeine Windows-Steuerelement-Unterstützung für Statusleiste Anpassung und zusätzliche Funktionen nutzen. `CStatusBar` Memberfunktionen geben Ihnen die meisten Funktionen des allgemeinen Windows-Steuerelemente; allerdings beim Aufruf `GetStatusBarCtrl`, Sie können den Statusleisten erteilen, sogar ein höherer Merkmale der Statusleiste Windows 95-und Windows 98. Beim Aufruf `GetStatusBarCtrl`, er wird zurückgegeben, einen Verweis auf ein `CStatusBarCtrl` Objekt. Finden Sie unter [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) für Weitere Informationen zum Entwerfen von Symbolleisten, die allgemeine Windows-Steuerelemente verwenden. Weitere allgemeine Informationen über allgemeine Steuerelemente finden Sie unter [Standardsteuerelementen](http://msdn.microsoft.com/library/windows/desktop/bb775493) im Windows SDK.  
  
 Das Framework speichert Indikatoreninformationen in einem Array mit den am weitesten links stehende Indikator an Position 0. Beim Erstellen einer Statusleiste verwenden Sie ein Array von Zeichenfolgen-IDs, die das Framework die entsprechenden Indikatoren zuordnet. Sie können dann eine Zeichenfolgen-ID oder einen Index verwenden, einen Indikator für den Zugriff auf.  
  
 Standardmäßig ist der erste Indikator "elastisch": Es nimmt die Statusleiste Länge, die nicht von den anderen Indikator Bereichen verwendet, damit die anderen Bereiche rechts ausgerichtet werden.  
  
 Um eine Statusleiste zu erstellen, gehen Sie folgendermaßen vor:  
  
1.  Erstellen der `CStatusBar` Objekt.  
  
2.  Rufen Sie die [erstellen](#create) (oder [CreateEx](#createex)) Funktion, um das Fenster mit der Statusleiste wird erstellt und angefügt, die `CStatusBar` Objekt.  
  
3.  Rufen Sie [SetIndicators](#setindicators) jedes Indikators eine Zeichenfolgen-ID zugeordnet werden soll.  
  
 Es gibt drei Möglichkeiten, um den Text in einem Bereich mit der Statusleiste zu aktualisieren:  
  
1.  Rufen Sie [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) auf den Text im Bereich 0 nur zu aktualisieren.  
  
2.  Rufen Sie [CCmdUI::SetText](../../mfc/reference/ccmdui-class.md#settext) in der Statusleiste ON_UPDATE_COMMAND_UI-Handler.  
  
3.  Rufen Sie [SetPaneText aufgerufen wird](#setpanetext) auf den Text für einen beliebigen Bereich zu aktualisieren.  
  
 Rufen Sie [SetPaneStyle](#setpanestyle) aktualisieren Sie den Stil eines mit der Statusleiste angezeigt.  
  
 Weitere Informationen zur Verwendung von `CStatusBar`, finden Sie im Artikel [Status Befehlsleisten-Standardimplementierung in MFC](../../mfc/status-bar-implementation-in-mfc.md) und [technischer Hinweis 31: Steuerleisten](../../mfc/tn031-control-bars.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CStatusBar`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="commandtoindex"></a>  CStatusBar::CommandToIndex  
 Ruft den Index der Indikator für eine angegebene ID  
  
```  
int CommandToIndex(UINT nIDFind) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nIDFind*  
 Zeichenfolgen-ID des Indikators, dessen Index ist, abgerufen werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des Indikators, wenn erfolgreich; 1, wenn nicht erfolgreich war.  
  
### <a name="remarks"></a>Hinweise  
 Der Index des ersten Indikators ist 0.  
  
##  <a name="create"></a>  CStatusBar::Create  
 Erstellt eine Statusleiste (ein untergeordnetes Fenster) und ordnet sie der `CStatusBar` Objekt.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Parameter  
 *pParentWnd*  
 Zeiger auf die [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, dessen Windows-Fenster das übergeordnete Element der Statusleiste ist.  
  
 *dwStyle*  
 Die Statusleiste. Zusätzlich zu den standardmäßigen Windows [Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles), diese Stile werden unterstützt.  
  
- CBRS_TOP Steuerleiste ist am Anfang des Rahmenfensters.  
  
- CBRS_BOTTOM Steuerleiste wird am unteren Rand Frame-Fensters.  
  
- CBRS_NOALIGN Steuerleiste ist nicht neu angeordnet, wenn die übergeordnetem Element geändert wird.  
  
 *nID*  
 Die Symbolleiste untergeordneten Fensters-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Außerdem wird die erste Schriftart und legt den Status der Höhe des Balkens einen Standardwert.  
  
##  <a name="createex"></a>  CStatusBar:: CreateEx  
 Mit dieser Funktion wird zum Erstellen einer Statusleiste (ein untergeordnetes Fenster), und ordnen sie die `CStatusBar` Objekt.  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = 0,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Parameter  
 *pParentWnd*  
 Zeiger auf die [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, dessen Windows-Fenster das übergeordnete Element der Statusleiste ist.  
  
 *dwCtrlStyle*  
 Weitere Formate für die Erstellung der eingebetteten [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) Objekt. Der Standardwert gibt an, eine Statusleiste, ohne einen Größenziehpunkt oder eine QuickInfo zu unterstützen. Status Leiste Stile unterstützt werden:  
  
- SBARS_SIZEGRIP Statusleisten-Steuerelement enthält einen Größenziehpunkt am rechten Ende der Statusleiste an. Ein Größenziehpunkt ist vergleichbar mit einem Rahmen; Es ist ein rechteckigen Bereichs, der der Benutzer kann klicken und ziehen Sie zum Ändern der Größe des übergeordneten Fensters.  
  
- SBT_TOOLTIPS die Statusleiste unterstützt QuickInfos.  
  
 Weitere Informationen zu diesen Formaten finden Sie unter [Einstellungen für CStatusBarCtrl](../../mfc/settings-for-the-cstatusbarctrl.md).  
  
 *dwStyle*  
 Der Status Standardstil der Statusleiste. Der Standardwert gibt an, dass eine sichtbare Statusleiste am unteren Rand des Rahmenfensters erstellt werden. Wenden Sie eine beliebige Kombination von Steuerelementtypen aufgeführt, die der Statusleiste [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles) und [CDialogBar::Create](../../mfc/reference/cdialogbar-class.md#create). Dieser Parameter sollte jedoch immer die Stile WS_CHILD und WS_VISIBLE enthalten.  
  
 *nID*  
 Die Statusleiste untergeordneten Fensters-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion auch legt die anfängliche Schriftart und den Status der Höhe des Balkens einen Standardwert.  
  
 Verwendung `CreateEx`, anstelle von [erstellen](#create), wenn bestimmte Formate während der Erstellung der eingebetteten Statusleisten-Steuerelement vorhanden sein müssen. Legen Sie z. B. *DwCtrlStyle* auf SBT_TOOLTIPS zum Anzeigen von QuickInfos in einem Status Leiste-Objekt.  
  
##  <a name="cstatusbar"></a>  CStatusBar::CStatusBar  
 Erstellt ein `CStatusBar` Objekt, eine Statusleiste Standardschriftart bei Bedarf erstellt, und die Schriftartmerkmale auf Standardwerte festgelegt.  
  
```  
CStatusBar();
```  
  
##  <a name="drawitem"></a>  CStatusBar::DrawItem  
 Diese Memberfunktion wird durch das Framework, wenn sich ein Darstellungsaspekt eines ein ownerdrawn-Statusleiste ändert sich aufgerufen.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 *lpDrawItemStruct*  
 Ein Zeiger auf eine [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) -Struktur, die Informationen über den Typ der Zeichnung erforderlich.  
  
### <a name="remarks"></a>Hinweise  
 Die `itemAction` Mitglied der `DRAWITEMSTRUCT` Struktur definiert die Zeichnen-Aktion, die ausgeführt werden soll. Überschreiben Sie diese Memberfunktion zum Implementieren der Zeichnung für ein Ownerdrawn- `CStatusBar` Objekt. Die Anwendung muss alle Device Interface (GDI) Grafikobjekten ausgewählt, für der Anzeigekontext in bereitgestellten wiederherstellen *LpDrawItemStruct* vor dem Beenden des diese Memberfunktion.  
  
##  <a name="getitemid"></a>  CStatusBar::GetItemID  
 Gibt die ID des Indikators gemäß *nIndex*.  
  
```  
UINT GetItemID(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Der Index des Indikators, deren ID wird abgerufen werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die ID des Indikators gemäß *nIndex*.  
  
##  <a name="getitemrect"></a>  CStatusBar::GetItemRect  
 Kopiert die Koordinaten des Indikators gemäß *nIndex* in der Struktur verweist *LpRect*.  
  
```  
void GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Der Index des Indikators, dessen Rechteckkoordinaten sind, abgerufen werden sollen.  
  
 *lpRect*  
 Verweist auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur oder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das die Koordinaten des Indikators gemäß erhält *nIndex*.  
  
### <a name="remarks"></a>Hinweise  
 Koordinaten werden in Pixel relativ zur linken oberen Ecke der Statusleiste.  
  
##  <a name="getpaneinfo"></a>  CStatusBar::GetPaneInfo  
 Legt *nID*, *nStyle*, und *CxWidth* auf die ID, Stil und die Breite des Indikatorbereichs an der vom angegebenen Position *nIndex*.  
  
```  
void GetPaneInfo(
    int nIndex,  
    UINT& nID,  
    UINT& nStyle,  
    int& cxWidth) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Der Index der Bereich, dessen Informationen abgerufen werden sollen, ist.  
  
 *nID*  
 Verweis auf eine "uint", die auf die ID des Bereichs festgelegt wird.  
  
 *nStyle*  
 Verweis auf eine "uint", die den Stil des Bereichs festgelegt wird.  
  
 *cxWidth*  
 Verweis auf eine ganze Zahl, die auf die Breite des Bereichs festgelegt wird.  
  
##  <a name="getpanestyle"></a>  CStatusBar::GetPaneStyle  
 Rufen Sie diese Memberfunktion um den Stil der Statusleiste Bereich abzurufen.  
  
```  
UINT GetPaneStyle(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Der Index des Bereichs, dessen Format ist abgerufen werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Format der Statusleiste gemäß *nIndex*.  
  
### <a name="remarks"></a>Hinweise  
 Format des Bereichs bestimmt, wie der Bereich angezeigt wird.  
  
 Eine Liste der verfügbaren zeigerformate von Statusleisten, finden Sie unter [erstellen](#create).  
  
##  <a name="getpanetext"></a>  CStatusBar::GetPaneText  
 Rufen Sie diese Memberfunktion zum Abrufen des Texts, der in einem Bereich mit der Statusleiste angezeigt wird.  
  
```  
CString GetPaneText(int nIndex) const;  void GetPaneText(int nIndex, CString& rString) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Der Index des Bereichs, dessen Text ist, abgerufen werden sollen.  
  
 *rString*  
 Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt mit dem Text abgerufen werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` Objekt, das den Bereich Text enthält.  
  
### <a name="remarks"></a>Hinweise  
 Die zweite Form dieses Members-Funktion füllt eine `CString` Objekt mit dem Zeichenfolgentext.  
  
##  <a name="getstatusbarctrl"></a>  GetStatusBarCtrl  
 Diese Memberfunktion ermöglicht den direkten Zugriff auf die zugrunde liegenden Standardsteuerelements.  
  
```  
CStatusBarCtrl& GetStatusBarCtrl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Enthält einen Verweis auf eine [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `GetStatusBarCtrl` die Funktionalität des allgemeinen Windows-Steuerelements von Statusleiste nutzen und die Unterstützung nutzen [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) Statusleiste Anpassung bereit. Z. B. mit dem allgemeinen Steuerelement, können Sie ein Stils, das einen Größenziehpunkt auf der Statusleiste inklusive, angeben, oder Sie können ein Format, um die Statusleiste am oberen Rand der Clientbereich des übergeordneten Fensters angezeigt angeben.  
  
 Weitere allgemeine Informationen über allgemeine Steuerelemente finden Sie unter [Standardsteuerelementen](http://msdn.microsoft.com/library/windows/desktop/bb775493) im Windows SDK.  
  
##  <a name="setindicators"></a>  CStatusBar:: SetIndicators  
 Legt jedes Indikators-ID auf den Wert, der durch das entsprechende Element im Array angegebenen *LpIDArray*, lädt der Zeichenfolgenressource, die durch jede ID angegeben und setzt des Indikators Text in der Zeichenfolge.  
  
```  
BOOL SetIndicators(
    const UINT* lpIDArray,  
    int nIDCount);
```  
  
### <a name="parameters"></a>Parameter  
 *lpIDArray*  
 Ein Zeiger auf ein Array von IDs.  
  
 *nIDCount*  
 Anzahl der Elemente im Array verweist *LpIDArray*.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
##  <a name="setpaneinfo"></a>  CStatusBar::SetPaneInfo  
 Legt den angegebenen Indikatorbereichs auf eine neue ID, Stil und die Breite fest.  
  
```  
void SetPaneInfo(
    int nIndex,  
    UINT nID,  
    UINT nStyle,  
    int cxWidth);
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Der Index des Indikatorbereichs, dessen Format ist, festgelegt werden.  
  
 *nID*  
 Neue ID für den Bereich des Indikators.  
  
 *nStyle*  
 Neue Formatvorlage für den Bereich des Indikators.  
  
 *cxWidth*  
 Neue Breite für den Bereich des Indikators.  
  
### <a name="remarks"></a>Hinweise  
 Die folgenden Indikator Stile werden unterstützt:  
  
- SBPS_NOBORDERS Nein 3D Rahmen um den Bereich.  
  
- Reverse-SBPS_POPOUT Rahmen, damit der Text "out holt."  
  
- Zeichnen von Text SBPS_DISABLED führen nicht.  
  
- SBPS_STRETCH Stretch Bereich zum Ausfüllen von nicht belegtem Speicherplatzes. Nur pro Statusleiste einen Bereich für dieses Format.  
  
- SBPS_NORMAL Nein Stretch "," Rahmen "oder" Popup-".  
  
##  <a name="setpanestyle"></a>  CStatusBar::SetPaneStyle  
 Rufen Sie diese Memberfunktion um den Stil des Bereichs einer Statusleiste festzulegen.  
  
```  
void SetPaneStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Der Index des Bereichs, dessen Format ist, festgelegt werden.  
  
 *nStyle*  
 Die Art des Bereich, dessen Format festgelegt werden, ist.  
  
### <a name="remarks"></a>Hinweise  
 Format des Bereichs bestimmt, wie der Bereich angezeigt wird.  
  
 Eine Liste der verfügbaren zeigerformate von Statusleisten, finden Sie unter [SetPaneInfo](#setpaneinfo).  
  
##  <a name="setpanetext"></a>  CStatusBar::SetPaneText  
 Rufen Sie diese Memberfunktion zum Festlegen des Texts im Bereich der Zeichenfolge verweist *LpszNewText*.  
  
```  
BOOL SetPaneText(
    int nIndex,  
    LPCTSTR lpszNewText,  
    BOOL bUpdate = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Der Index des Bereichs, dessen Text ist, festgelegt werden.  
  
 *lpszNewText*  
 Ein Zeiger auf den neuen Bereich Text.  
  
 *bUpdate*  
 Bei "true", wird der Bereich ungültig gemacht werden, nachdem der Text selbst festgelegt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf `SetPaneText`, müssen Sie einen UI-Update-Handler um den neuen Text in der Statusleiste anzeigen, hinzufügen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#176](../../mfc/codesnippet/cpp/cstatusbar-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#177](../../mfc/codesnippet/cpp/cstatusbar-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#178](../../mfc/codesnippet/cpp/cstatusbar-class_3.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel jeder](../../visual-cpp-samples.md)   
 [MFC-Beispiel DLGCBR32](../../visual-cpp-samples.md)   
 [CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CStatusBarCtrl-Klasse](../../mfc/reference/cstatusbarctrl-class.md)   
 [CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)
