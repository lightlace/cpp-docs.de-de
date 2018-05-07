---
title: CMFCRibbonQuickAccessToolBarDefaultState Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::AddCommand
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], CMFCRibbonQuickAccessToolBarDefaultState
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], AddCommand
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], CopyFrom
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], RemoveAll
ms.assetid: eca99200-b87b-47ba-b2e8-2f3f2444b176
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9baeb204234a6df50be062c5944e9b257cb2d2c9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcribbonquickaccesstoolbardefaultstate-class"></a>CMFCRibbonQuickAccessToolBarDefaultState-Klasse
Eine Hilfsklasse, die Standardstatus für die Symbolleiste für den Schnellzugriff verwaltet, die auf der menübandleiste befindet ( [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonQuickAccessToolBarDefaultState  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState](#cmfcribbonquickaccesstoolbardefaultstate)|Erstellt ein `CMFCRibbonQuickAccessToolbarDefaultState`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand)|Fügt einen Befehl auf den Standardstatus für die Symbolleiste für den Schnellzugriff an. Dadurch wird die Symbolleiste selbst nicht geändert.|  
|[CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom](#copyfrom)|Kopiert die Eigenschaften einer Symbolleiste für den Schnellzugriff.|  
|[CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll](#removeall)|Entfernt alle Befehle aus der Symbolleiste für den Schnellzugriff an. Dadurch wird die Symbolleiste selbst nicht geändert.|  
  
## <a name="remarks"></a>Hinweise  
 Nachdem Sie die Symbolleiste für den Schnellzugriff in Ihrer Anwendung erstellen, sollten Sie durch Aufrufen von Standardzustand festlegen [CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate). Dieser Standardstatus wird wiederhergestellt, wenn ein Benutzer klickt auf die **zurücksetzen** Schaltfläche auf der **anpassen** Seite Ihrer Anwendung **Optionen** (Dialogfeld).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CMFCRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen von ein Objekt von der `CMFCRibbonQuickAccessToolbarDefaultState` Klasse und wie Sie einen Befehl auf den Standardstatus für die Symbolleiste für den Schnellzugriff hinzufügen.  
  
 [!code-cpp[NVC_MFC_RibbonApp#21](../../mfc/reference/codesnippet/cpp/cmfcribbonquickaccesstoolbardefaultstate-class_1.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxribbonquickaccesstoolbar.h  
  
##  <a name="addcommand"></a>  CMFCRibbonQuickAccessToolBarDefaultState::AddCommand  
 Fügt einen Befehl auf den Standardstatus für die Symbolleiste für den Schnellzugriff an.  
  
```  
void AddCommand(
    UINT uiCmd,  
    BOOL bIsVisible=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `[in] uiCmd`  
 Gibt die Befehls-ID.  
  
 `[in] bIsVisible`  
 Legt die Sichtbarkeit des Befehls fest, wenn die Symbolleiste für den Schnellzugriff im Standardzustand befindet.  
  
### <a name="remarks"></a>Hinweise  
 Die CMFCRibbonQuickAccessToolBarDefaultState einen Befehl hinzufügen, führt drei Ergebnisse. Zunächst wird jede hinzugefügte Befehl in der Dropdownliste auf der rechten Seite der Symbolleiste für den Schnellzugriff aufgeführt. Ein Benutzer kann auf diese Weise hinzufügen und entfernen den Befehl aus der Symbolleiste für den Schnellzugriff. Zweitens die Symbolleiste für den Schnellzugriff wird zurückgesetzt und zeigt nur die Befehle, die aufgelistet werden als sichtbar im Standardzustand klickt der Benutzer die **zurücksetzen** Schaltfläche der **anpassen** (Dialogfeld). Dritte, wenn Sie nicht aufgerufen haben [CMFCRibbonBar::SetQuickAccessCommands](../../mfc/reference/cmfcribbonbar-class.md#setquickaccesscommands), der Symbolleiste für den Schnellzugriff verwendet die sichtbaren Befehlen aus dieser Liste als die standardmäßige sichtbaren Befehlen der ersten Ausführung ein Benutzer die Anwendung. Nachdem Sie alle Befehle, die Sie möchten hinzugefügt haben, rufen Sie [CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate) dieser Instanz als der Standardstatus für die Symbolleiste für den Schnellzugriff von diesem Menübandleiste festgelegt.  
  
##  <a name="copyfrom"></a>  CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom  
 Kopiert die Eigenschaften einer Symbolleiste für den Schnellzugriff.  
  
```  
void CopyFrom(const CMFCRibbonQuickAccessToolBarDefaultState& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `src`  
 Ein Verweis auf die Quelle `CMFCRibbonQuickAccessToolBarDefaultState` Objekt, das kopiert.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kopiert jeden Befehl aus der Quelldatenbank `CMFCRibbonQuickAccessToolBarDefaultState` Objekt, das dieses Objekt unter Verwendung der [CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand) Methode.  
  
##  <a name="cmfcribbonquickaccesstoolbardefaultstate"></a>  CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState  
 Erstellt die Symbolleiste für den Schnellzugriff Standard-Status-Objekt.  
  
```  
CMFCRibbonQuickAccessToolBarDefaultState();
```  
  
### <a name="remarks"></a>Hinweise  
 Wird standardmäßig die Liste der Befehle, die neue Instanz der [CMFRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md) enthält ist leer.  
  
##  <a name="removeall"></a>  CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll  
 Löscht die Liste der Standardbefehle in der Symbolleiste für den Schnellzugriff an.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion entfernt aus dieser Instanz alle Befehle, die die vorherigen Aufrufe von [CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand) hinzugefügt.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBar-Klasse](../../mfc/reference/cmfcribbonbar-class.md)
