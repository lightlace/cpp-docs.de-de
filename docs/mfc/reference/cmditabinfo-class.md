---
title: Klasse CMDITabInfo | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CMDITabInfo class
- CMDITabInfo class, constructor
ms.assetid: 988ae1b7-4f7f-4239-b88f-7e28b3291c5e
caps.latest.revision: 37
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
ms.openlocfilehash: a45532c98d5da7d89d27e3d29d9b40075cf0376f
ms.lasthandoff: 02/24/2017

---
# <a name="cmditabinfo-class"></a>CMDITabInfo-Klasse
Die `CMDITabInfo` Klasse wird verwendet, um Parameter zu übergeben [CMDIFrameWndEx::EnableMDITabbedGroups](../../mfc/reference/cmdiframewndex-class.md#enablemditabbedgroups) Methode. Legen Sie Member dieser Klasse fest, um das Verhalten der MDI-Gruppen im Registerkartenformat zu steuern.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMDITabInfo   
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMDITabInfo::CMDITabInfo`|Standardkonstruktor|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMDITabInfo::Serialize](#serialize)|Liest oder schreibt dieses Objekt aus einem oder in ein Archiv.|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMDITabInfo::m_bActiveTabCloseButton;](#m_bactivetabclosebutton_)|Gibt an, ob ein **schließen** Schaltfläche auf die Bezeichnung der aktiven Registerkarte angezeigt wird.|  
|[CMDITabInfo::m_bAutoColor](#m_bautocolor)|Gibt an, ob die Registerkarten MDI-Farbe.|  
|[CMDITabInfo::m_bDocumentMenu](#m_bdocumentmenu)|Gibt an, ob die Gruppe von Registerkarten ein Popup-Menü angezeigt, die zeigt eine Liste der geöffneten Dokumente oder Bildlaufschaltflächen angezeigt.|  
|[CMDITabInfo::m_bEnableTabSwap](#m_benabletabswap)|Gibt an, ob der Benutzer die Positionen der Registerkarten ziehen austauschen kann.|  
|[CMDITabInfo::m_bFlatFrame](#m_bflatframe)|Gibt an, ob Registerkarten einen flachen Frame.|  
|[CMDITabInfo::m_bTabCloseButton](#m_btabclosebutton)|Gibt an, ob jede registerkartenbezeichnung ein **schließen** Schaltfläche.|  
|[CMDITabInfo::m_bTabCustomTooltips](#m_btabcustomtooltips)|Gibt an, ob QuickInfos aktiviert sind.|  
|[CMDITabInfo::m_bTabIcons](#m_btabicons)|Gibt an, ob Symbole auf MDI-Registerkarten anzuzeigen.|  
|[CMDITabInfo::m_nTabBorderSize](#m_ntabbordersize)|Gibt die Rahmengröße der einzelnen Registerkartenfenster.|  
|[CMDITabInfo::m_style](#m_style)|Gibt den Stil der registerkartenbezeichnungen.|  
|[CMDITabInfo::m_tabLocation](#m_tablocation)|Gibt an, ob die Bezeichnungen Registerkarten am oberen oder unteren Rand der Seite befinden.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse gibt die Parameter der MDI-Registerkartengruppen, die das Framework erstellt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die Werte für die verschiedenen Membervariablen in festlegen `CMDITabInfo` Klasse.  
  
 [!code-cpp[NVC_MFC_MDITab&#1;](../../mfc/reference/codesnippet/cpp/cmditabinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CMDITabInfo](../../mfc/reference/cmditabinfo-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxmdiclientareawnd.h  
  
##  <a name="m_bactivetabclosebutton_"></a>CMDITabInfo::m_bActiveTabCloseButton;  
 Gibt an, ob ein **schließen** Schaltfläche auf die Bezeichnung der aktiven Registerkarte angezeigt wird.  
  
```  
BOOL m_bActiveTabCloseButton;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `TRUE`, zeigt die Bezeichnung der aktiven Registerkarte ein **schließen** Schaltfläche. Die **schließen** Schaltfläche wird von der rechten oberen Ecke des Registerkartenbereichs entfernt. Andernfalls wird die Bezeichnung der aktiven Registerkarte nicht angezeigt ein **schließen** Schaltfläche. Die **schließen** Schaltfläche in der rechten oberen Ecke des Registerkartenbereichs angezeigt.  
  
##  <a name="m_bautocolor"></a>CMDITabInfo::m_bAutoColor  
 Gibt an, ob jede MDI-Registerkarte eine eigene Farbe aufweist.  
  
```  
BOOL m_bAutoColor;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `TRUE`, jede Registerkarte weist eine eigene Farbe. Der Satz von Farben wird von der MFC-Bibliothek verwaltet. Andernfalls werden die Registerkarten in Weiß angezeigt. Der Standardwert ist `FALSE`.  
  
##  <a name="m_bdocumentmenu"></a>CMDITabInfo::m_bDocumentMenu  
 Gibt an, ob jede Registerkarte ein Popup-Menü angezeigt, die eine Liste der geöffneten Dokumente am rechten Rand des Registerkartenbereichs angezeigt wird.  
  
```  
BOOL m_bDocumentMenu;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `TRUE`, jede Registerkarte Windows zeigt ein Popup-Menü, das eine Liste der geöffneten Dokumente am rechten Rand des Registerkartenbereichs; Andernfalls wird das Registerkartenfenster Bildlaufschaltflächen am rechten Rand des Registerkartenbereichs. Der Standardwert ist `FALSE`.  
  
##  <a name="m_benabletabswap"></a>CMDITabInfo::m_bEnableTabSwap  
 Gibt an, ob der Benutzer die Positionen der Registerkarten ziehen austauschen kann.  
  
```  
BOOL m_bEnableTabSwap;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `TRUE`, der Benutzer kann die Registerkarten Positionen ändern, indem Sie die Registerkarten ziehen. Andernfalls kann nicht der Benutzer die Registerkarten Positionen ändern. Der Standardwert ist `TRUE`.  
  
##  <a name="m_bflatframe"></a>CMDITabInfo::m_bFlatFrame  
 Gibt an, ob jede im Registerkartenfenster einen flachen Rahmen hat.  
  
```  
BOOL m_bFlatFrame;  
```  
  
##  <a name="m_btabclosebutton"></a>CMDITabInfo::m_bTabCloseButton  
 Gibt an, ob jede Registerkartenfenster zeigt eine **schließen** Schaltfläche.  
  
```  
BOOL m_bTabCloseButton;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `TRUE`, zeigt jede im Registerkartenfenster der **schließen** auf den rechten Rand der Registerkarte auf die Schaltfläche. Andernfalls die **schließen** Schaltfläche wird nicht angezeigt. Der Standardwert ist `TRUE`.  
  
##  <a name="m_btabcustomtooltips"></a>CMDITabInfo::m_bTabCustomTooltips  
 Gibt an, ob die Registerkarten in QuickInfos.  
  
```  
BOOL m_bTabCustomTooltips;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `TRUE`, die Anwendung sendet eine `AFX_WM_ON_GET_TAB_TOOLTIP` Nachricht an den Hauptframe. Sie können diese Nachricht behandeln, indem die `ON_REGISTERED_MESSAGE` Makro.  
  
##  <a name="m_btabicons"></a>CMDITabInfo::m_bTabIcons  
 Gibt an, ob Symbole auf MDI-Registerkarten anzuzeigen.  
  
```  
BOOL m_bTabIcons;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `TRUE`, Symbole werden auf jeder MDI-Registerkarte angezeigt. Andernfalls werden die Symbole nicht auf Registerkarten angezeigt. Der Standardwert ist `FALSE`.  
  
##  <a name="m_ntabbordersize"></a>CMDITabInfo::m_nTabBorderSize  
 Rahmengröße angibt in Pixel der einzelnen Registerkartenfenster.  
  
```  
int m_nTabBorderSize;  
```  
  
### <a name="remarks"></a>Hinweise  
 [CMFCVisualManager::GetMDITabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize) gibt den Standardwert zurück.  
  
##  <a name="m_style"></a>CMDITabInfo::m_style  
 Gibt den Stil der registerkartenbezeichnungen.  
  
```  
CMFCTabCtrl::Style m_style  
```  
  
### <a name="remarks"></a>Hinweise  
 Geben Sie einen der folgenden Formate für die registerkartenbezeichnungen:  
  
 `STYLE_3D`  
 -3D-Format.  
  
 `STYLE_3D_ONENOTE`  
 Microsoft OneNote-Format.  
  
 `STYLE_3D_VS2005`  
 Microsoft Visual Studio 2005-Format.  
  
 `STYLE_3D_SCROLLED`  
 -3D-Format mit Rechteck registerkartenbezeichnungen.  
  
 `STYLE_FLAT_SHARED_HORZ_SCROLL`  
 Flache mit freigegebenen horizontale Bildlaufleiste angezeigt.  
  
 `STYLE_3D_ROUNDED_SCROLL`  
 -3D-Format mit round registerkartenbezeichnungen.  
  
##  <a name="m_tablocation"></a>CMDITabInfo::m_tabLocation  
 Gibt an, ob die Bezeichnungen Registerkarten am oberen oder unteren Rand der Seite befinden.  
  
```  
CMFCTabCtrl::Location m_tabLocation;  
```  
  
### <a name="remarks"></a>Hinweise  
 Auf den Registerkarten eine der folgenden Speicherort Flags anwenden:  
  
-   LOCATION_BOTTOM: die Bezeichnungen Registerkarten befinden sich am unteren Rand der Seite.  
  
-   LOCATION_TOP: die Registerkarten Bezeichnungen befinden sich am oberen Rand der Seite  
  
##  <a name="serialize"></a>CMDITabInfo::Serialize  
 Liest oder schreibt dieses Objekt aus einem Archiv oder in ein Archiv.  
  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `ar`  
 Ein [CArchive-Klasse](../../mfc/reference/carchive-class.md) zu serialisierende Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [CMDIFrameWndEx-Klasse](../../mfc/reference/cmdiframewndex-class.md)   
 [MDI-Gruppen im Registerkartenformat](../../mfc/mdi-tabbed-groups.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)

