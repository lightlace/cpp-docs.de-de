---
title: CMFCRibbonQuickAccessToolBarDefaultState-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 0ee9ee6a600e4a552e90cd5901340c3759d52a59
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702779"
---
# <a name="cmfcribbonquickaccesstoolbardefaultstate-class"></a>CMFCRibbonQuickAccessToolBarDefaultState-Klasse
Eine Hilfsklasse, die standardmäßig für die Symbolleiste für den Schnellzugriff verwaltet, die in der menübandleiste befindet ( [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)).  
  
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
|[CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand)|Fügt einen Befehl auf den Standardstatus für die Symbolleiste für den Schnellzugriff an. Dies ändert sich nicht auf die Symbolleiste selbst aus.|  
|[CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom](#copyfrom)|Kopiert die Eigenschaften einer Symbolleiste für den Schnellzugriff.|  
|[CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll](#removeall)|Entfernt alle Befehle aus der Symbolleiste für den Schnellzugriff an. Dies ändert sich nicht auf die Symbolleiste selbst aus.|  
  
## <a name="remarks"></a>Hinweise  
 Nachdem Sie die Symbolleiste für den Schnellzugriff in Ihrer Anwendung erstellt, es wird empfohlen, Sie Standardzustand durch Aufrufen von [CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate). Dieser Standardstatus wird wiederhergestellt, wenn ein Benutzer klickt der **zurücksetzen** Schaltfläche der **anpassen** auf der Seite Ihrer Anwendungsverzeichnis **Optionen** Dialogfeld.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CMFCRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, wie zum Erstellen eines Objekts von der `CMFCRibbonQuickAccessToolbarDefaultState` -Klasse und das Hinzufügen ein Befehls auf den Standardstatus für die Symbolleiste für den Schnellzugriff.  
  
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
 *[in] uiCmd*  
 Gibt die Befehls-ID.  
  
 *[in] bIsVisible*  
 Legt die Sichtbarkeit des Befehls fest, wenn die Symbolleiste für den Schnellzugriff im Standardzustand befindet.  
  
### <a name="remarks"></a>Hinweise  
 Hinzufügen eines Befehls zu den CMFCRibbonQuickAccessToolBarDefaultState erfüllt drei Ergebnisse. Zunächst wird jede hinzugefügte Befehl in der Dropdownliste auf der rechten Seite der Symbolleiste für den Schnellzugriff aufgeführt. Auf diese Weise kann Benutzer ganz einfach hinzufügen oder entfernen diesen Befehl aus der Symbolleiste für den Schnellzugriff. Zweitens: Symbolleiste für den Schnellzugriff ist zurücksetzen, um anzuzeigen nur für diejenigen Befehle, die aufgeführt sind als sichtbar im Standardzustand klickt der Benutzer die **zurücksetzen** Schaltfläche der **anpassen** Dialogfeld. Dritte, wenn Sie nicht aufgerufen haben [CMFCRibbonBar::SetQuickAccessCommands](../../mfc/reference/cmfcribbonbar-class.md#setquickaccesscommands), Symbolleiste für den Schnellzugriff verwendet die sichtbaren Befehlen aus dieser Liste als den standardmäßigen sichtbaren Befehlen beim ersten Ausführen die Anwendung durch den Benutzer. Nachdem Sie alle Befehle, die Sie möchten hinzugefügt haben, rufen [CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate) dieser Instanz als die Standardwerte für die Symbolleiste für den Schnellzugriff der diesem Menüband festlegen.  
  
##  <a name="copyfrom"></a>  CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom  
 Kopiert die Eigenschaften einer Symbolleiste für den Schnellzugriff.  
  
```  
void CopyFrom(const CMFCRibbonQuickAccessToolBarDefaultState& src);
```  
  
### <a name="parameters"></a>Parameter  
*src*<br/>
[in] Ein Verweis auf die `CMFCRibbonQuickAccessToolBarDefaultState` Objekt, das kopiert.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kopiert jeden Befehl aus der Quelle `CMFCRibbonQuickAccessToolBarDefaultState` Objekt, das dieses Objekt mit der [CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand) Methode.  
  
##  <a name="cmfcribbonquickaccesstoolbardefaultstate"></a>  CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState  
 Erstellt das Zustandsobjekt, das standardmäßig die Symbolleiste für Schnellzugriff an.  
  
```  
CMFCRibbonQuickAccessToolBarDefaultState();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig die Liste der Befehle, die neue Instanz der [CMFRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md) enthält ist leer.  
  
##  <a name="removeall"></a>  CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll  
 Löscht die Liste der Standardbefehle in der Symbolleiste für den Schnellzugriff an.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird von dieser Instanz entfernt, alle Befehle, die den vorherigen Aufrufen zum [CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand) hinzugefügt.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBar-Klasse](../../mfc/reference/cmfcribbonbar-class.md)
