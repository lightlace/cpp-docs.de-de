---
title: Klasse CMFCRibbonMainPanel | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonMainPanel
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonMainPanel class
ms.assetid: 1af78798-5e75-4365-9c81-a54aa5679602
caps.latest.revision: 23
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 3fc37a953e62e6ea90de8402b7f2912b06967e13
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonmainpanel-class"></a>CMFCRibbonMainPanel-Klasse
Implementiert einen Menübandbereich, der anzeigt, wenn Sie auf die [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonMainPanel : public CMFCRibbonPanel  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCRibbonMainPanel::CMFCRibbonMainPanel`|Standardkonstruktor|  
|`CMFCRibbonMainPanel::~CMFCRibbonMainPanel`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonMainPanel::Add](#add)|Im linken Bereich des Schaltflächenbereich Anwendung hinzugefügt ein Menübandelement. (Überschreibt [CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add).)|  
|[CMFCRibbonMainPanel::AddRecentFilesList](#addrecentfileslist)|Fügt eine Zeichenfolge zum Listenmenü zuletzt verwendete Dateien hinzu.|  
|[CMFCRibbonMainPanel::AddToBottom](#addtobottom)|Unteren Bereich des Bereichs Anwendung Menüband hinzugefügt ein Menübandelement.|  
|[CMFCRibbonMainPanel::AddToRight](#addtoright)|Rechten Bereich der Anwendung Schaltflächenbereich hinzugefügt ein Menübandelement.|  
|`CMFCRibbonMainPanel::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCRibbonMainPanel::GetCommandsFrame](#getcommandsframe)|Gibt ein Rechteck, das den Clientbereich der Menüband-Hauptbereich darstellt.|  
|`CMFCRibbonMainPanel::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
  
## <a name="remarks"></a>Hinweise  
 Zeigt das Framework die `CMFCRibbonMainPanel` Wenn Sie das Feld "Anwendung" öffnen. Es enthält drei Bereiche:  
  
-   Der linke Bereich enthält Befehle, die Dateien zugeordnet sind, z. B. **öffnen**, **speichern**, **Drucken**, und **schließen**. Rufen Sie zum Hinzufügen eines Befehls in diesen Bereich [CMFCRibbonMainPanel::Add](#add).  
  
-   Der rechte Bereich enthält Optionen, die mit dem Befehl ändern, den Sie im linken Bereich klicken. Beispielsweise, wenn Sie auf **speichern** aus im linken Bereich Rechte Dateitypen anzeigen kann. Um diesem Bereich ein Element hinzuzufügen, rufen Sie [CMFCRibbonMainPanel::AddToRight](#addtoright).  
  
-   Der untere Bereich enthält Schaltflächen, mit denen Sie die Einstellungen der Anwendung zu ändern und das Programm zu beenden. Um diesem Bereich ein Element hinzuzufügen, rufen Sie [CMFCRibbonMainPanel::AddToBottom](#addtobottom).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)  
  
 [CMFCRibbonMainPanel](../../mfc/reference/cmfcribbonmainpanel-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxRibbonMainPanel.h  
  
##  <a name="a-nameadda--cmfcribbonmainpaneladd"></a><a name="add"></a>CMFCRibbonMainPanel::Add  
 Im linken Bereich des Schaltflächenbereich Anwendung hinzugefügt ein Menübandelement.  
  
```  
virtual void Add(CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out]`pElem`  
 Ein Zeiger auf das Menübandelement den Hauptbereich hinzu.  
  
### <a name="remarks"></a>Hinweise  
 Im Bereich hinzugefügt ein Menübandelement. Mit dieser Methode hinzugefügte Elemente werden in der linken Spalte der Hauptbereich befinden.  
  
##  <a name="a-nameaddrecentfileslista--cmfcribbonmainpaneladdrecentfileslist"></a><a name="addrecentfileslist"></a>CMFCRibbonMainPanel::AddRecentFilesList  
 Fügt eine Zeichenfolge zum Listenmenü zuletzt verwendete Dateien hinzu.  
  
```  
void AddRecentFilesList(
    LPCTSTR lpszLabel,  
    int nWidth = 300);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszLabel`  
 Gibt die Zeichenfolge, die die Liste der zuletzt geöffneten Dateien hinzugefügt.  
  
 `nWidth`  
 Gibt die Breite in Pixel der aktuellen Liste Dateibereich.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameaddtobottoma--cmfcribbonmainpaneladdtobottom"></a><a name="addtobottom"></a>CMFCRibbonMainPanel::AddToBottom  
 Unteren Bereich des Bereichs Anwendung Menüband hinzugefügt ein Menübandelement.  
  
```  
void AddToBottom(CMFCRibbonMainPanelButton* pElem);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out]`pElem`  
 Ein Zeiger auf die Multifunktionsleisten-Element am Ende der Hauptbereich hinzufügen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameaddtorighta--cmfcribbonmainpaneladdtoright"></a><a name="addtoright"></a>CMFCRibbonMainPanel::AddToRight  
 Rechten Bereich der Anwendung Schaltflächenbereich hinzugefügt ein Menübandelement.  
  
```  
void AddToRight(
    CMFCRibbonBaseElement* pElem,  
    int nWidth = 300);
```  
  
### <a name="parameters"></a>Parameter  
 `pElem`  
 Ein Zeiger auf ein Menübandelement rechts neben den Hauptbereich hinzugefügt werden.  
  
 `nWidth`  
 Gibt die Breite in Pixel im rechten Bereich.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion im rechten Bereich ein Menübandelement hinzu. Im rechte Bereich in der Regel zeigt die Liste der zuletzt geöffneten Dateien, aber Sie können eine beliebige andere Menübandelement hier hinzufügen.  
  
##  <a name="a-namegetcommandsframea--cmfcribbonmainpanelgetcommandsframe"></a><a name="getcommandsframe"></a>CMFCRibbonMainPanel::GetCommandsFrame  
 Gibt ein Rechteck, das den Clientbereich der Menüband-Hauptbereich darstellt.  
  
```  
CRect GetCommandsFrame() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Rechteck, das den Clientbereich der Menüband-Hauptbereich darstellt.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonPanel-Klasse](../../mfc/reference/cmfcribbonpanel-class.md)

