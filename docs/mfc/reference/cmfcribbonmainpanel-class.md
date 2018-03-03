---
title: CMFCRibbonMainPanel Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::Add
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddRecentFilesList
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToBottom
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToRight
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::GetCommandsFrame
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonMainPanel [MFC], Add
- CMFCRibbonMainPanel [MFC], AddRecentFilesList
- CMFCRibbonMainPanel [MFC], AddToBottom
- CMFCRibbonMainPanel [MFC], AddToRight
- CMFCRibbonMainPanel [MFC], GetCommandsFrame
ms.assetid: 1af78798-5e75-4365-9c81-a54aa5679602
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f8b5508abdc90c4c566d078f2f75c30822c7a18e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcribbonmainpanel-class"></a>CMFCRibbonMainPanel-Klasse
Implementiert einen Menübandbereich, der anzeigt, wenn Sie auf die [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonMainPanel : public CMFCRibbonPanel  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCRibbonMainPanel::CMFCRibbonMainPanel`|Standardkonstruktor|  
|`CMFCRibbonMainPanel::~CMFCRibbonMainPanel`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonMainPanel::Add](#add)|Links von der Anwendung Schaltflächenbereich hinzugefügt ein Menübandelement. (Überschreibt [cmfcribbonpanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add).)|  
|[CMFCRibbonMainPanel::AddRecentFilesList](#addrecentfileslist)|Fügt eine Textzeichenfolge für das Menü, Liste zuletzt verwendete Dateien.|  
|[CMFCRibbonMainPanel::AddToBottom](#addtobottom)|Unteren Bereich der Anwendung Menübandbereich hinzugefügt ein Menübandelement.|  
|[CMFCRibbonMainPanel::AddToRight](#addtoright)|Bereich rechts von der Anwendung Schaltflächenbereich hinzugefügt ein Menübandelement.|  
|`CMFCRibbonMainPanel::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCRibbonMainPanel::GetCommandsFrame](#getcommandsframe)|Gibt ein Rechteck, das den Clientbereich der Menüband-Hauptbereich darstellt.|  
|`CMFCRibbonMainPanel::GetThisClass`|Durch das Framework verwendet wird, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
  
## <a name="remarks"></a>Hinweise  
 Zeigt das Framework der `CMFCRibbonMainPanel` beim Öffnen der Anwendung-Bereich. Es enthält drei Bereiche:  
  
-   Der linke Bereich enthält Dateien, wie z. B. zugeordneten Befehle **öffnen**, **speichern**, **Drucken**, und **schließen**. Rufen Sie zum Hinzufügen eines Befehls in diesen Bereich [CMFCRibbonMainPanel::Add](#add).  
  
-   Der rechte Bereich enthält Optionen, die den Befehl zu ändern, den Sie im linken Bereich klicken. Angenommen, Sie klicken Sie auf **speichern unter** im linken Bereich den rechte Bereich verfügbaren Dateitypen anzeigen kann. Um ein Element in diesen Bereich hinzuzufügen, rufen Sie [CMFCRibbonMainPanel::AddToRight](#addtoright).  
  
-   Der untere Bereich enthält Schaltflächen, mit denen Sie die Einstellungen der Anwendung zu ändern und das Programm zu beenden. Um ein Element in diesen Bereich hinzuzufügen, rufen Sie [CMFCRibbonMainPanel::AddToBottom](#addtobottom).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)  
  
 [CMFCRibbonMainPanel](../../mfc/reference/cmfcribbonmainpanel-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxRibbonMainPanel.h  
  
##  <a name="add"></a>CMFCRibbonMainPanel::Add  
 Links von der Anwendung Schaltflächenbereich hinzugefügt ein Menübandelement.  
  
```  
virtual void Add(CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out]`pElem`  
 Ein Zeiger auf das Menübandelement der Hauptbereich hinzu.  
  
### <a name="remarks"></a>Hinweise  
 Fügt ein Menübandelement in den Bereich an. Mit dieser Methode hinzugefügte Elemente werden in der linken Spalte der Bereiche "main" befinden.  
  
##  <a name="addrecentfileslist"></a>CMFCRibbonMainPanel::AddRecentFilesList  
 Fügt eine Textzeichenfolge für das Menü, Liste zuletzt verwendete Dateien.  
  
```  
void AddRecentFilesList(
    LPCTSTR lpszLabel,  
    int nWidth = 300);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszLabel`  
 Gibt die Zeichenfolge, die Dateiliste der zuletzt geöffneten hinzugefügt.  
  
 `nWidth`  
 Gibt die Breite in Pixel der aktuellen Liste Dateibereich an.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="addtobottom"></a>CMFCRibbonMainPanel::AddToBottom  
 Unteren Bereich der Anwendung Menübandbereich hinzugefügt ein Menübandelement.  
  
```  
void AddToBottom(CMFCRibbonMainPanelButton* pElem);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out]`pElem`  
 Ein Zeiger auf das Menübandelement an das Ende der Hauptbereich hinzufügen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="addtoright"></a>CMFCRibbonMainPanel::AddToRight  
 Bereich rechts von der Anwendung Schaltflächenbereich hinzugefügt ein Menübandelement.  
  
```  
void AddToRight(
    CMFCRibbonBaseElement* pElem,  
    int nWidth = 300);
```  
  
### <a name="parameters"></a>Parameter  
 `pElem`  
 Ein Zeiger auf ein Menübandelement rechts neben der Hauptbereich hinzugefügt werden.  
  
 `nWidth`  
 Gibt die Breite in Pixel im rechten Bereich an.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion im rechten Bereich ein Menübandelement hinzu. Im rechte Bereich zeigt die Dateiliste der zuletzt geöffneten in der Regel an, aber Sie können eine beliebige andere Menübandelement hier hinzufügen.  
  
##  <a name="getcommandsframe"></a>CMFCRibbonMainPanel::GetCommandsFrame  
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
