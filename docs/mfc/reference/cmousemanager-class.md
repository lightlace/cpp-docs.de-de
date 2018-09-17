---
title: CMouseManager-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 38dcb010df79e0a5c5a54079b4c98021cc406c8d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720270"
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
|[CMouseManager::AddView](#addview)|Fügt eine `CView` -Objekt an die **Anpassung** Dialogfeld. Die **Anpassung** Dialogfeld ermöglicht dem Benutzer, einen Befehl für jede der aufgelisteten Ansichten einen Doppelklick zugeordnet werden soll.|  
|[CMouseManager::GetViewDblClickCommand](#getviewdblclickcommand)|Gibt zurück, den Befehl, der ausgeführt wird, wenn der Benutzer in der angegebenen Ansicht doppelklickt.|  
|[CMouseManager::GetViewIconId](#getviewiconid)|Gibt das Symbol, das die angegebenen anzeigen-ID zugeordnet ist|  
|[CMouseManager::GetViewIdByName](#getviewidbyname)|Gibt die ID des angegebenen Ansichtsnamens zugeordnet.|  
|[CMouseManager::GetViewNames](#getviewnames)|Ruft eine Liste von Namen für alle hinzugefügten anzeigen.|  
|[CMouseManager::LoadState](#loadstate)|Lädt die `CMouseManager` Status aus der Windows-Registrierung.|  
|[CMouseManager::SaveState](#savestate)|Schreibt die `CMouseManager` Zustands, in der Windows-Registrierung.|  
|[CMouseManager::SetCommandForDblClk](#setcommandfordblclk)|Ordnet den angegebenen Befehl und der angegebenen Ansicht.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMouseManager` Klasse verwaltet eine Auflistung von `CView` Objekte. Jede Ansicht wird durch einen Namen und eine ID identifiziert. Diese Ansichten werden angezeigt, der **Anpassung** Dialogfeld. Der Benutzer kann den Befehl, der mit einer beliebigen Ansicht über verknüpft ist Ändern der **Anpassung** Dialogfeld. Der zugeordnete Befehl ausgeführt wird, wenn der Benutzer in dieser Ansicht doppelklickt. Sie müssen zur Unterstützung hinsichtlich der Codierung verarbeiten, die WM_LBUTTONDBLCLK-Nachricht und der Aufruf der [CWinAppEx::OnViewDoubleClick](../../mfc/reference/cwinappex-class.md#onviewdoubleclick) -Funktion in der Code dafür `CView` Objekt...  
  
 Erstellen Sie keine `CMouseManager` Objekt manuell. Durch das Framework der Anwendung wird erstellt werden. Es werden auch automatisch zerstört, wenn der Benutzer die Anwendung beendet wird. Um einen Zeiger auf die Maus-Manager für Ihre Anwendung zu erhalten, rufen [CWinAppEx::GetMouseManager](../../mfc/reference/cwinappex-class.md#getmousemanager).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMouseManager`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxmousemanager.h  
  
##  <a name="addview"></a>  CMouseManager::AddView  
 Registriert eine [CView](../../mfc/reference/cview-class.md) Objekt mit der [CMouseManager-Klasse](../../mfc/reference/cmousemanager-class.md) um benutzerdefinierte Mausverhalten zu unterstützen.  
  
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
*iViewId*<br/>
[in] Eine Sicht-ID.  
  
*uiViewNameResId*<br/>
[in] Eine Zeichenfolge Ressourcen-ID, die den Namen der Sicht verweist.  
  
*uiIconId*<br/>
[in] Eine Sicht Symbol-ID.  
  
*iId*<br/>
[in] Eine Sicht-ID.  
  
*lpszViewName*<br/>
[in] Der Name einer Ansicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Um benutzerdefinierte Mausverhalten zu unterstützen, muss in eine Ansicht registriert werden die `CMouseManager` Objekt. Jedes Objekt abgeleitet der `CView` -Klasse mit dem Mauszeiger-Manager registriert werden kann. Der Zeichenfolge und einer Ansicht zugeordnete Symbol angezeigt, der **Maus** auf der Registerkarte der **anpassen** im Dialogfeld.  
  
 Es liegt in der Verantwortung des Programmierers erstellen und verwalten die Ansicht IDs wie z. B. *iViewId* und *iId*.  
  
 Weitere Informationen dazu, wie Sie benutzerdefinierte Mausverhalten bereitzustellen, finden Sie unter [Anpassen von Tastatur und Maus](../../mfc/keyboard-and-mouse-customization.md).  
  
### <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, wie einen Zeiger auf Abrufen einer `CMouseManager` -Objekt unter Verwendung der `CWinAppEx::GetMouseManager` Methode und die `AddView` -Methode in der die `CMouseManager` Klasse. Dieser Codeausschnitt ist Teil der [Zustandsauflistung Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StateCollection#4](../../mfc/reference/codesnippet/cpp/cmousemanager-class_1.cpp)]  
  
##  <a name="getviewdblclickcommand"></a>  CMouseManager::GetViewDblClickCommand  
 Gibt zurück, den Befehl, der ausgeführt wird, wenn der Benutzer in der angegebenen Ansicht doppelklickt.  
  
```  
UINT GetViewDblClickCommand(int iId) const;  
```  
  
### <a name="parameters"></a>Parameter  
*iId*<br/>
[in] Die Sicht-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Befehls-ID, wenn die Ansicht mit einem Befehl zugeordnet ist; andernfalls 0.  
  
##  <a name="getviewiconid"></a>  CMouseManager::GetViewIconId  
 Ruft das Symbol für den eine Sicht-ID.  
  
```  
UINT GetViewIconId(int iViewId) const;  
```  
  
### <a name="parameters"></a>Parameter  
*iViewId*<br/>
[in] Die Sicht-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Ressourcenbezeichner Symbol, wenn erfolgreich; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schlägt fehl, wenn die Ansicht mit nicht zuerst registriert ist [CMouseManager::AddView](#addview).  
  
##  <a name="getviewidbyname"></a>  CMouseManager::GetViewIdByName  
 Ruft die durch einen Sichtnamen verknüpfte ID ab.  
  
```  
int GetViewIdByName(LPCTSTR lpszName) const;  
```  
  
### <a name="parameters"></a>Parameter  
*Wert*<br/>
[in] Name der Ansicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Sicht mit der ID bei erfolgreicher Ausführung; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode durchsucht Ansichten mit registriert [CMouseManager::AddView](#addview).  
  
##  <a name="getviewnames"></a>  CMouseManager::GetViewNames  
 Ruft eine Liste aller registrierten Ansicht Namen.  
  
```  
void GetViewNames(CStringList& listOfNames) const;  
```  
  
### <a name="parameters"></a>Parameter  
*listOfNames*<br/>
[out] Ein Verweis auf `CStringList` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode füllt den Parameter `listOfNames` mit den Namen aller Ansichten, die mit registriert [CMouseManager::AddView](#addview).  
  
##  <a name="loadstate"></a>  CMouseManager::LoadState  
 Lädt den Zustand der der [CMouseManager-Klasse](../../mfc/reference/cmousemanager-class.md) aus der Registrierung.  
  
```  
BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>Parameter  
*lpszProfileName*<br/>
[in] Ein Pfad eines Registrierungsschlüssels.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Zustandsinformationen aus der Registrierung geladen umfasst die registrierten Ansichten Ansichtsbezeichner und die zugehörigen Befehle. Wenn der Parameter *LpszProfileName* NULL ist, diese Funktion lädt die `CMouseManager` Daten aus der Registrierung-Standardspeicherort, gesteuert durch die [CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md).  
  
 In den meisten Fällen müssen Sie nicht diese Funktion nicht direkt aufrufen. Sie wird als Teil der Initialisierungsprozess Arbeitsbereich aufgerufen. Weitere Informationen zu den Initialisierungsprozess für den Arbeitsbereich, finden Sie unter [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate).  
  
##  <a name="savestate"></a>  CMouseManager::SaveState  
 Schreibt den Status der [CMouseManager-Klasse](../../mfc/reference/cmousemanager-class.md) an der Registrierung.  
  
```  
BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>Parameter  
*lpszProfileName*<br/>
[in] Ein Pfad eines Registrierungsschlüssels.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Statusinformationen in die Registrierung geschrieben enthält alle registrierten Ansichten, Ansichtsbezeichner und die zugehörigen Befehle. Wenn der Parameter *LpszProfileName* NULL ist, diese Funktion schreibt die `CMouseManager` Daten an den Registrierung-Standardspeicherort, gesteuert durch die [CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md).  
  
 In den meisten Fällen müssen Sie nicht diese Funktion nicht direkt aufrufen. Sie wird als Teil des Serialisierungsprozesses Arbeitsbereich aufgerufen. Weitere Informationen zu den Serialisierungsprozess Arbeitsbereich, finden Sie unter [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate).  
  
##  <a name="setcommandfordblclk"></a>  CMouseManager::SetCommandForDblClk  
 Ordnet einen benutzerdefinierten Befehl mit einer Ansicht, die zuerst mit der Maus-Manager registriert ist.  
  
```  
void SetCommandForDblClk(
    int iViewId,  
    UINT uiCmd);
```  
  
### <a name="parameters"></a>Parameter  
*iViewId*<br/>
[in] Der Ansichtsbezeichner.  
  
*uiCmd*<br/>
[in] Der Befehlsbezeichner.  
  
### <a name="remarks"></a>Hinweise  
 Um eine Ansicht für einen benutzerdefinierten Befehl zugeordnet werden soll, müssen Sie zuerst die Ansicht registrieren, mit [CMouseManager::AddView](#addview). Die `AddView` Methode erfordert ein Ansichtsbezeichner als Eingabeparameter. Wenn Sie eine Ansicht registriert haben, können Sie aufrufen `CMouseManager::SetCommandForDblClk` mit der gleichen Ansicht Bezeichner Eingabeparameter, die Sie an `AddView`. Danach, wenn der Benutzer den Mauszeiger über die registrierten Ansicht doppelklickt, die Anwendung wird führen Sie den Befehl erkennbar *UiCmd.* Um das benutzerdefinierte Maus-Verhalten zu unterstützen, müssen Sie auch anpassen, die Ansicht mit der Maus-Manager registriert. Weitere Informationen zu benutzerdefinierten Mausverhalten, finden Sie unter [Anpassen von Tastatur und Maus](../keyboard-and-mouse-customization.md).  
  
 Wenn *UiCmd* festgelegt ist, 0, die angegebene Ansicht ist nicht mehr einem Befehl zugeordnet.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)   
 [Anpassen von Tastatur und Maus](../../mfc/keyboard-and-mouse-customization.md)



