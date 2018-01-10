---
title: CMouseManager Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMouseManager
- AFXMOUSEMANAGER/CMouseManager
- AFXMOUSEMANAGER/CMouseManager::AddView
- AFXMOUSEMANAGER/CMouseManager::GetViewDblClickCommand
- AFXMOUSEMANAGER/CMouseManager::GetViewIconId
- AFXMOUSEMANAGER/CMouseManager::GetViewIdByName
- AFXMOUSEMANAGER/CMouseManager::GetViewNames
- AFXMOUSEMANAGER/CMouseManager::LoadState
- AFXMOUSEMANAGER/CMouseManager::SaveState
- AFXMOUSEMANAGER/CMouseManager::SetCommandForDblClk
dev_langs: C++
helpviewer_keywords:
- CMouseManager [MFC], AddView
- CMouseManager [MFC], GetViewDblClickCommand
- CMouseManager [MFC], GetViewIconId
- CMouseManager [MFC], GetViewIdByName
- CMouseManager [MFC], GetViewNames
- CMouseManager [MFC], LoadState
- CMouseManager [MFC], SaveState
- CMouseManager [MFC], SetCommandForDblClk
ms.assetid: a4d05017-4e44-4a40-8b57-4ece0de20481
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f50b74731089346a9675b5340ba0ea1a0b2879f4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmousemanager-class"></a>CMouseManager-Klasse
Ermöglicht einem Benutzer, unterschiedliche Befehle einem bestimmten zuordnen [CView](../../mfc/reference/cview-class.md) Objekt, wenn der Benutzer in dieser Ansicht doppelklickt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMouseManager : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMouseManager::AddView](#addview)|Fügt eine `CView` -Objekt an die **Anpassung** (Dialogfeld). Die **Anpassung** Dialogfeld ermöglicht dem Benutzer, einen Befehl für jede der aufgeführten Ansichten Doppelklick zugeordnet werden soll.|  
|[CMouseManager::GetViewDblClickCommand](#getviewdblclickcommand)|Gibt den Befehl, der ausgeführt wird, wenn der Benutzer innerhalb der angegebenen Ansicht doppelklickt.|  
|[CMouseManager::GetViewIconId](#getviewiconid)|Gibt das Symbol, das die angegebene Ansicht-ID zugeordnet ist|  
|[CMouseManager::GetViewIdByName](#getviewidbyname)|Gibt die ID des angegebenen Ansichtsnamens zugeordnet.|  
|[CMouseManager::GetViewNames](#getviewnames)|Ruft eine Liste der Ansichtsnamen aller hinzugefügte ab.|  
|[CMouseManager::LoadState](#loadstate)|Lädt die `CMouseManager` Status aus der Windows-Registrierung.|  
|[CMouseManager::SaveState](#savestate)|Schreibt die `CMouseManager` Zustands, in der Windows-Registrierung.|  
|[CMouseManager::SetCommandForDblClk](#setcommandfordblclk)|Ordnet den angegebenen Befehl und der angegebenen Ansicht.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMouseManager` Klasse verwaltet eine Auflistung von `CView` Objekte. Jede Ansicht wird durch einen Namen und eine ID identifiziert. Diese Sichten werden angezeigt, der **Anpassung** (Dialogfeld). Der Benutzer kann den Befehl aus, die mit einer beliebigen Ansicht über anfallen ändern die **Anpassung** (Dialogfeld). Der zugeordnete Befehl wird ausgeführt, wenn der Benutzer in dieser Ansicht doppelklickt. Unterstützung von dies hinsichtlich der Codierung unterscheiden, müssen Sie verarbeiten die `WM_LBUTTONDBLCLK` Nachricht und rufen die [CWinAppEx::OnViewDoubleClick](../../mfc/reference/cwinappex-class.md#onviewdoubleclick) im Code für diese Funktion `CView` Objekt...  
  
 Sie sollten keine erstellen eine `CMouseManager` Objekt manuell. Durch das Framework der Anwendung wird erstellt werden. Es wird auch automatisch zerstört, wenn der Benutzer die Anwendung beendet wird. Rufen Sie zum Abrufen eines Zeigers auf die Maus-Manager für Ihre Anwendung [CWinAppEx::GetMouseManager](../../mfc/reference/cwinappex-class.md#getmousemanager).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMouseManager`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxmousemanager.h  
  
##  <a name="addview"></a>CMouseManager::AddView  
 Registriert eine [CView](../../mfc/reference/cview-class.md) -Objekt mit den [CMouseManager Klasse](../../mfc/reference/cmousemanager-class.md) benutzerdefinierten Verhalten zu unterstützen.  
  
```  
BOOL AddView(
    int iViewId,  
    UINT uiViewNameResId,  
    UINT uiIconId = 0);

 
BOOL AddView(
    int iId,  
    LPCTSTR lpszViewName,  
    UINT uiIconId = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iViewId`  
 Eine Sicht-ID.  
  
 [in] `uiViewNameResId`  
 Eine Zeichenfolge Ressourcen-ID, die den Namen der Sicht verweist.  
  
 [in] `uiIconId`  
 Eine Sicht Symbol-ID.  
  
 [in] `iId`  
 Eine Sicht-ID.  
  
 [in] `lpszViewName`  
 Ein Sichtname.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Benutzerdefinierte Mausverhalten zu unterstützen, muss eine Ansicht mit registriert werden die `CMouseManager` Objekt. Jedes Objekt abgeleitet wird, aus der `CView` Klasse mit der Maus-Manager registriert werden kann. Der Zeichenfolge und einer Ansicht zugeordnete Symbol angezeigt, der **Maus** auf der Registerkarte die **anpassen** (Dialogfeld).  
  
 Es liegt in der Verantwortung des Programmierers erstellen und verwalten die Ansicht IDs wie z. B. `iViewId` und `iId`.  
  
 Weitere Informationen zum benutzerdefinierten Verhalten bereitzustellen, finden Sie unter [Anpassen von Tastatur und Maus](../../mfc/keyboard-and-mouse-customization.md).  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie einen Zeiger zum Abrufen einer `CMouseManager` Objekt mithilfe der `CWinAppEx::GetMouseManager` Methode und die `AddView` Methode in der `CMouseManager` Klasse. Dieser Codeausschnitt ist Teil der [Auflistung Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StateCollection#4](../../mfc/reference/codesnippet/cpp/cmousemanager-class_1.cpp)]  
  
##  <a name="getviewdblclickcommand"></a>CMouseManager::GetViewDblClickCommand  
 Gibt den Befehl, der ausgeführt wird, wenn der Benutzer innerhalb der angegebenen Ansicht doppelklickt.  
  
```  
UINT GetViewDblClickCommand(int iId) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iId`  
 Die Sicht-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Befehlsbezeichner, ob die Sicht einen Befehl zugeordnet ist; andernfalls 0.  
  
##  <a name="getviewiconid"></a>CMouseManager::GetViewIconId  
 Ruft das Symbol, das eine Ansicht-ID zugeordnet ist  
  
```  
UINT GetViewIconId(int iViewId) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iViewId`  
 Die Sicht-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Symbol Ressourcenbezeichner, wenn erfolgreich; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schlägt fehl, wenn die Sicht nicht zuerst registriert ist [CMouseManager::AddView](#addview).  
  
##  <a name="getviewidbyname"></a>CMouseManager::GetViewIdByName  
 Ruft einen Sichtnamen zugeordnete Ansicht-ID ab.  
  
```  
int GetViewIdByName(LPCTSTR lpszName) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszName`  
 Name der Ansicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Sicht mit der ID im Erfolgsfall; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sucht, Sichten, die mithilfe der registriert [CMouseManager::AddView](#addview).  
  
##  <a name="getviewnames"></a>CMouseManager::GetViewNames  
 Ruft eine Liste aller registrierten Sichtnamen ab.  
  
```  
void GetViewNames(CStringList& listOfNames) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `listOfNames`  
 Ein Verweis auf `CStringList` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode füllt die Parameter `listOfNames` mit den Namen aller Ansichten, die mithilfe der registriert [CMouseManager::AddView](#addview).  
  
##  <a name="loadstate"></a>CMouseManager::LoadState  
 Lädt den Zustand der der [CMouseManager Klasse](../../mfc/reference/cmousemanager-class.md) aus der Registrierung.  
  
```  
BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Ein Pfad eines Registrierungsschlüssels.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Zustandsinformationen aus der Registrierung geladen enthält registrierten Ansichten, steuerelementspezifischer Ansichtsbezeichner und die zugehörigen Befehle. Wenn der Parameter `lpszProfileName` ist `NULL`, diese Funktion lädt die `CMouseManager` Daten aus den Standardspeicherort für die Registrierung von gesteuert der [CWinAppEx Class](../../mfc/reference/cwinappex-class.md).  
  
 In den meisten Fällen müssen Sie nicht diese Funktion nicht direkt aufrufen. Sie wird als Teil der Initialisierungsvorgang Arbeitsbereich aufgerufen. Weitere Informationen über den Initialisierungsprozess Arbeitsbereich finden Sie unter [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate).  
  
##  <a name="savestate"></a>CMouseManager::SaveState  
 Schreibt den Status der [CMouseManager Klasse](../../mfc/reference/cmousemanager-class.md) an der Registrierung.  
  
```  
BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Ein Pfad eines Registrierungsschlüssels.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Statusinformationen in die Registrierung geschrieben enthält alle registrierten Ansichten, steuerelementspezifischer Ansichtsbezeichner und die zugehörigen Befehle. Wenn der Parameter `lpszProfileName` ist `NULL`, schreibt Sie diese Funktion die `CMouseManager` Daten an den Standardspeicherort für die Registrierung von gesteuert der [CWinAppEx Class](../../mfc/reference/cwinappex-class.md).  
  
 In den meisten Fällen müssen Sie nicht diese Funktion nicht direkt aufrufen. Sie wird als Teil des Serialisierungsprozesses Arbeitsbereich aufgerufen. Weitere Informationen zu den Serialisierungsprozess Arbeitsbereich, finden Sie unter [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate).  
  
##  <a name="setcommandfordblclk"></a>CMouseManager::SetCommandForDblClk  
 Ordnet einen benutzerdefinierten Befehl eine Sicht, die zuerst mit der Maus-Manager registriert ist.  
  
```  
void SetCommandForDblClk(
    int iViewId,  
    UINT uiCmd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iViewId`  
 Der Bezeichner.  
  
 [in] `uiCmd`  
 Der Befehlsbezeichner.  
  
### <a name="remarks"></a>Hinweise  
 Um eine Ansicht ein benutzerdefiniertes Befehls zuzuordnen, müssen Sie zuerst die Sicht registrieren, mit [CMouseManager::AddView](#addview). Die `AddView` Methode erfordert einen Bezeichner als Eingabeparameter. Nachdem Sie eine Sicht registriert haben, können Sie aufrufen `CMouseManager::SetCommandForDblClk` mit der gleichen Ansicht Bezeichner Eingabeparameter, die Sie an `AddView`. Danach, wenn der Benutzer die Maus in der registrierten Ansicht doppelklickt, die Anwendung wird führen Sie den Befehl erkennbar `uiCmd.` um das benutzerdefinierte Verhalten zu unterstützen, Sie müssen auch zum Anpassen der Ansicht mit der Maus-Manager registriert. Weitere Informationen zu benutzerdefinierten Verhalten, finden Sie unter [Anpassen von Tastatur und Maus]--Brokenlink--(.. / Maus-und-Tastatur-customization.md).  
  
 Wenn `uiCmd` festgelegt ist, 0, die angegebene Ansicht ist nicht mehr mit einem Befehl verknüpft.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)   
 [Anpassen von Tastatur und Maus](../../mfc/keyboard-and-mouse-customization.md)



