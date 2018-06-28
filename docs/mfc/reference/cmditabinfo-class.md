---
title: CMDITabInfo Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMDITabInfo
- AFXMDICLIENTAREAWND/CMDITabInfo
- AFXMDICLIENTAREAWND/CMDITabInfo::Serialize
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bAutoColor
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bDocumentMenu
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bEnableTabSwap
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bFlatFrame
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabCloseButton
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabCustomTooltips
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabIcons
- AFXMDICLIENTAREAWND/CMDITabInfo::m_nTabBorderSize
- AFXMDICLIENTAREAWND/CMDITabInfo::m_style
- AFXMDICLIENTAREAWND/CMDITabInfo::m_tabLocation
dev_langs:
- C++
helpviewer_keywords:
- CMDITabInfo [MFC], Serialize
- CMDITabInfo [MFC], m_bAutoColor
- CMDITabInfo [MFC], m_bDocumentMenu
- CMDITabInfo [MFC], m_bEnableTabSwap
- CMDITabInfo [MFC], m_bFlatFrame
- CMDITabInfo [MFC], m_bTabCloseButton
- CMDITabInfo [MFC], m_bTabCustomTooltips
- CMDITabInfo [MFC], m_bTabIcons
- CMDITabInfo [MFC], m_nTabBorderSize
- CMDITabInfo [MFC], m_style
- CMDITabInfo [MFC], m_tabLocation
ms.assetid: 988ae1b7-4f7f-4239-b88f-7e28b3291c5e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b3676db7cedbca1fe831e44c9ff7cf018360adc
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040052"
---
# <a name="cmditabinfo-class"></a>CMDITabInfo-Klasse
Die `CMDITabInfo` Klasse wird verwendet, um zum Übergeben von Parametern [CMDIFrameWndEx:: Enablemditabbedgroups](../../mfc/reference/cmdiframewndex-class.md#enablemditabbedgroups) Methode. Legen Sie Member dieser Klasse fest, um das Verhalten der MDI-Gruppen im Registerkartenformat zu steuern.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMDITabInfo   
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMDITabInfo::CMDITabInfo`|Standardkonstruktor|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMDITabInfo::Serialize](#serialize)|Liest oder schreibt dieses Objekt aus einem oder in ein Archiv.|  
  
### <a name="data-members"></a>Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CMDITabInfo::m_bActiveTabCloseButton;](#m_bactivetabclosebutton_)|Gibt an, ob eine **schließen** -Schaltfläche auf die Bezeichnung der aktiven Registerkarte angezeigt wird.|  
|[CMDITabInfo::m_bAutoColor](#m_bautocolor)|Gibt an, ob die Registerkarten MDI-Farbe.|  
|[CMDITabInfo::m_bDocumentMenu](#m_bdocumentmenu)|Gibt an, ob die Gruppe von Registerkarten ein Popupmenü anzeigt, die zeigt eine Liste der geöffneten Dokumente oder Bildlaufschaltflächen angezeigt.|  
|[CMDITabInfo::m_bEnableTabSwap](#m_benabletabswap)|Gibt an, ob der Benutzer die Position von Registerkarten durch Ziehen austauschen kann.|  
|[CMDITabInfo::m_bFlatFrame](#m_bflatframe)|Gibt an, ob Registerkarten einen Flatfile-Frame.|  
|[CMDITabInfo::m_bTabCloseButton](#m_btabclosebutton)|Gibt an, ob jede registerkartenbezeichnung zeigt eine **schließen** Schaltfläche.|  
|[CMDITabInfo::m_bTabCustomTooltips](#m_btabcustomtooltips)|Gibt an, ob benutzerdefinierte QuickInfos aktiviert sind.|  
|[CMDITabInfo::m_bTabIcons](#m_btabicons)|Gibt an, ob Symbole auf MDI-Registerkarten anzuzeigen.|  
|[CMDITabInfo::m_nTabBorderSize](#m_ntabbordersize)|Gibt die Rahmengröße eines einzelnen "Verwaltung".|  
|[CMDITabInfo::m_style](#m_style)|Gibt die Art der registerkartenbezeichnungen.|  
|[CMDITabInfo::m_tabLocation](#m_tablocation)|Gibt an, ob die Bezeichnungen für die Registerkarten am oberen oder unteren Rand der Seite befinden.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse gibt die Parameter der MDI-Registerkartengruppen, die das Framework erstellt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Festlegen der Werte der verschiedenen Membervariablen in `CMDITabInfo` Klasse.  
  
 [!code-cpp[NVC_MFC_MDITab#1](../../mfc/reference/codesnippet/cpp/cmditabinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CMDITabInfo](../../mfc/reference/cmditabinfo-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxmdiclientareawnd.h  
  
##  <a name="m_bactivetabclosebutton_"></a>  CMDITabInfo::m_bActiveTabCloseButton;  
 Gibt an, ob eine **schließen** -Schaltfläche auf die Bezeichnung der aktiven Registerkarte angezeigt wird.  
  
```  
BOOL m_bActiveTabCloseButton;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `TRUE`, zeigt die Bezeichnung der aktiven Registerkarte ein **schließen** Schaltfläche. Die **schließen** Schaltfläche aus der rechten oberen Ecke des Registerkartenbereichs entfernt werden. Andernfalls wird die Bezeichnung der aktiven Registerkarte nicht angezeigt ein **schließen** Schaltfläche. Die **schließen** Schaltfläche erscheint in der rechten oberen Ecke des Registerkartenbereichs.  
  
##  <a name="m_bautocolor"></a>  CMDITabInfo::m_bAutoColor  
 Gibt an, ob jede MDI-Registerkarte eine eigenen Farbe aufweist.  
  
```  
BOOL m_bAutoColor;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `TRUE`, jede Registerkarte des Arbeitsblattes einer eigenen Farbe. Der Satz von Farben wird von der MFC-Bibliothek verwaltet. Andernfalls werden die Registerkarten in Weiß angezeigt. Der Standardwert ist `FALSE`.  
  
##  <a name="m_bdocumentmenu"></a>  CMDITabInfo::m_bDocumentMenu  
 Gibt an, ob jede Registerkarte ein Popupmenü anzeigt, die eine Liste der geöffneten Dokumente am rechten Rand des Registerkartenbereichs angezeigt wird.  
  
```  
BOOL m_bDocumentMenu;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `TRUE`, jede Windows Registerkarte zeigt ein Popupmenü, das eine Liste der geöffneten Dokumente am rechten Rand des Registerkartenbereichs; angezeigt wird Andernfalls wird die "Verwaltung" Bildlaufschaltflächen am rechten Rand des Registerkartenbereichs angezeigt. Der Standardwert ist `FALSE`.  
  
##  <a name="m_benabletabswap"></a>  CMDITabInfo::m_bEnableTabSwap  
 Gibt an, ob der Benutzer die Position von Registerkarten durch Ziehen austauschen kann.  
  
```  
BOOL m_bEnableTabSwap;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `TRUE`, der Benutzer kann die Registerkarten Positionen durch Ziehen von Registerkarten ändern. Andernfalls kann nicht der Benutzer die Registerkarten Positionen ändern. Der Standardwert ist `TRUE`.  
  
##  <a name="m_bflatframe"></a>  CMDITabInfo::m_bFlatFrame  
 Gibt an, ob jede "Verwaltung" einen flachen Frame verfügt.  
  
```  
BOOL m_bFlatFrame;  
```  
  
##  <a name="m_btabclosebutton"></a>  CMDITabInfo::m_bTabCloseButton  
 Gibt an, ob jede "Verwaltung" zeigt eine **schließen** Schaltfläche.  
  
```  
BOOL m_bTabCloseButton;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `TRUE`, zeigt jede "Verwaltung" die **schließen** Schaltfläche am rechten Rand der Registerkarte. Andernfalls die **schließen** Schaltfläche nicht angezeigt wird. Der Standardwert ist `TRUE`.  
  
##  <a name="m_btabcustomtooltips"></a>  CMDITabInfo::m_bTabCustomTooltips  
 Gibt an, ob die Registerkarten QuickInfos anzuzeigen.  
  
```  
BOOL m_bTabCustomTooltips;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `TRUE`, die Anwendung sendet eine `AFX_WM_ON_GET_TAB_TOOLTIP` Nachricht zum Hauptframe. Sie können diese Nachricht behandeln, indem die `ON_REGISTERED_MESSAGE` Makro.  
  
##  <a name="m_btabicons"></a>  CMDITabInfo::m_bTabIcons  
 Gibt an, ob Symbole auf MDI-Registerkarten anzuzeigen.  
  
```  
BOOL m_bTabIcons;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `TRUE`, auf den einzelnen Registerkarten MDI werden Symbole angezeigt. Andernfalls werden die Symbole nicht auf Registerkarten angezeigt. Der Standardwert ist `FALSE`.  
  
##  <a name="m_ntabbordersize"></a>  CMDITabInfo::m_nTabBorderSize  
 Gibt an, der Border Size, der jede "Verwaltung" in Pixel.  
  
```  
int m_nTabBorderSize;  
```  
  
### <a name="remarks"></a>Hinweise  
 [CMFCVisualManager::GetMDITabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize) gibt den Standardwert zurück.  
  
##  <a name="m_style"></a>  CMDITabInfo::m_style  
 Gibt die Art der registerkartenbezeichnungen.  
  
```  
CMFCTabCtrl::Style m_style  
```  
  
### <a name="remarks"></a>Hinweise  
 Geben Sie einen der folgenden Formate für die registerkartenbezeichnungen:  
  
 `STYLE_3D`  
 3D-Format.  
  
 `STYLE_3D_ONENOTE`  
 Microsoft OneNote-Format.  
  
 `STYLE_3D_VS2005`  
 Microsoft Visual Studio 2005-Format.  
  
 `STYLE_3D_SCROLLED`  
 3D Stil mit registerkartenbezeichnungen Rechteck.  
  
 `STYLE_FLAT_SHARED_HORZ_SCROLL`  
 Flache mit freigegebenen horizontale Bildlaufleiste angezeigt.  
  
 `STYLE_3D_ROUNDED_SCROLL`  
 3D Stil mit round registerkartenbezeichnungen.  
  
##  <a name="m_tablocation"></a>  CMDITabInfo::m_tabLocation  
 Gibt an, ob die Bezeichnungen für die Registerkarten am oberen oder unteren Rand der Seite befinden.  
  
```  
CMFCTabCtrl::Location m_tabLocation;  
```  
  
### <a name="remarks"></a>Hinweise  
 Gelten Sie für die Registerkarten eine der folgenden Flags, Speicherort:  
  
-   LOCATION_BOTTOM: die Bezeichnungen Registerkarten befinden sich am unteren Rand der Seite.  
  
-   LOCATION_TOP: die Bezeichnungen Registerkarten befinden sich am oberen Rand der Seite  
  
##  <a name="serialize"></a>  CMDITabInfo::Serialize  
 Liest oder schreibt dieses Objekt aus einem Archiv oder in ein Archiv.  
  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *Ar*  
 Ein [CArchive-Klasse](../../mfc/reference/carchive-class.md) zu serialisierende Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [CMDIFrameWndEx-Klasse](../../mfc/reference/cmdiframewndex-class.md)   
 [MDI-Gruppen im Registerkartenformat](../../mfc/mdi-tabbed-groups.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)
