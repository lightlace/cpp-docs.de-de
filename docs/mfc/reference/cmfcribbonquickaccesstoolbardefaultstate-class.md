---
title: Klasse CMFCRibbonQuickAccessToolBarDefaultState | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState class
ms.assetid: eca99200-b87b-47ba-b2e8-2f3f2444b176
caps.latest.revision: 28
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
ms.openlocfilehash: 211e8d897de923e7f07df389b0e9e7218cf45872
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonquickaccesstoolbardefaultstate-class"></a>CMFCRibbonQuickAccessToolBarDefaultState-Klasse
Eine Hilfsklasse, die standardmäßig für die Symbolleiste für den Schnellzugriff verwaltet, die in der menübandleiste befindet ( [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonQuickAccessToolBarDefaultState  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState](#cmfcribbonquickaccesstoolbardefaultstate)|Erstellt ein `CMFCRibbonQuickAccessToolbarDefaultState`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand)|Fügt den Befehl auf den Standardstatus für die Symbolleiste für den Schnellzugriff. Dadurch wird die Symbolleiste selbst nicht geändert.|  
|[CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom](#copyfrom)|Kopiert die Eigenschaften einer Symbolleiste für den Schnellzugriff.|  
|[CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll](#removeall)|Entfernt alle Befehle aus der Symbolleiste für den Schnellzugriff. Dadurch wird die Symbolleiste selbst nicht geändert.|  
  
## <a name="remarks"></a>Hinweise  
 Nach der Erstellung der Symbolleiste für den Schnellzugriff in Ihrer Anwendung sollten Sie den Standardzustand durch Aufrufen von festlegen [CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate). Dieser Standardstatus wird wiederhergestellt, wenn ein Benutzer klickt auf die **zurücksetzen** auf die Schaltfläche der **anpassen** Seite Ihrer Anwendung **Optionen** Dialogfeld.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CMFCRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Objekt vom Erstellen der `CMFCRibbonQuickAccessToolbarDefaultState` -Klasse und das Hinzufügen ein Befehls auf den Standardstatus für die Symbolleiste für den Schnellzugriff.  
  
 [!code-cpp[NVC_MFC_RibbonApp&21;](../../mfc/reference/codesnippet/cpp/cmfcribbonquickaccesstoolbardefaultstate-class_1.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxribbonquickaccesstoolbar.h  
  
##  <a name="a-nameaddcommanda--cmfcribbonquickaccesstoolbardefaultstateaddcommand"></a><a name="addcommand"></a>CMFCRibbonQuickAccessToolBarDefaultState::AddCommand  
 Fügt den Befehl auf den Standardstatus für die Symbolleiste für den Schnellzugriff.  
  
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
 Hinzufügen eines Befehls zu den CMFCRibbonQuickAccessToolBarDefaultState führt drei Ergebnisse aus. Zunächst wird jeder hinzugefügten Befehl in der Dropdownliste auf der rechten Seite der Symbolleiste für den Schnellzugriff aufgeführt. Auf diese Weise kann Benutzer problemlos hinzufügen oder Entfernen von diesen Befehl aus der Symbolleiste für den Schnellzugriff. Zweitens Symbolleiste für den Schnellzugriff ist zurücksetzen, um anzuzeigen nur die Befehle, die aufgelistet werden als sichtbar im Standardzustand klickt der Benutzer die **zurücksetzen** -Schaltfläche in der **anpassen** Dialogfeld. Dritte, wenn Sie nicht aufgerufen haben [CMFCRibbonBar::SetQuickAccessCommands](../../mfc/reference/cmfcribbonbar-class.md#setquickaccesscommands), Symbolleiste für den Schnellzugriff verwendet die Standardbefehle aus dieser Liste als die Standardbefehle sichtbar ersten Mal ein Benutzer die Anwendung ausführt. Nachdem Sie alle Befehle, die Sie möchten hinzugefügt haben, rufen Sie [CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate) dieser Instanz als Standardeinstellungen für die Symbolleiste für den Schnellzugriff der Multifunktionsleiste Bar festgelegt.  
  
##  <a name="a-namecopyfroma--cmfcribbonquickaccesstoolbardefaultstatecopyfrom"></a><a name="copyfrom"></a>CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom  
 Kopiert die Eigenschaften einer Symbolleiste für den Schnellzugriff.  
  
```  
void CopyFrom(const CMFCRibbonQuickAccessToolBarDefaultState& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `src`  
 Ein Verweis auf die Quelle `CMFCRibbonQuickAccessToolBarDefaultState` Objekt, das kopiert.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kopiert jeden Befehl von der Quelle `CMFCRibbonQuickAccessToolBarDefaultState` Objekt zu diesem Objekt mithilfe der [CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand) Methode.  
  
##  <a name="a-namecmfcribbonquickaccesstoolbardefaultstatea--cmfcribbonquickaccesstoolbardefaultstatecmfcribbonquickaccesstoolbardefaultstate"></a><a name="cmfcribbonquickaccesstoolbardefaultstate"></a>CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState  
 Erstellt das Standardobjekt des Status für den Schnellzugriff.  
  
```  
CMFCRibbonQuickAccessToolBarDefaultState();
```  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung die Liste der Befehle, die der neuen Instanz von [CMFRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md) enthält ist leer.  
  
##  <a name="a-nameremovealla--cmfcribbonquickaccesstoolbardefaultstateremoveall"></a><a name="removeall"></a>CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll  
 Löscht die Liste der Standardbefehle in der Symbolleiste für den Schnellzugriff.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion entfernt aus dieser Instanz alle Befehle, die den vorherigen Aufrufen zum [CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand) hinzugefügt.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBar-Klasse](../../mfc/reference/cmfcribbonbar-class.md)

