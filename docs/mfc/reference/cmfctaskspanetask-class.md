---
title: Cmfctaskspanetask-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask::CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask::SetACCData
- AFXTASKSPANE/CMFCTasksPaneTask::m_bAutoDestroyWindow
- AFXTASKSPANE/CMFCTasksPaneTask::m_bIsBold
- AFXTASKSPANE/CMFCTasksPaneTask::m_dwUserData
- AFXTASKSPANE/CMFCTasksPaneTask::m_hwndTask
- AFXTASKSPANE/CMFCTasksPaneTask::m_nIcon
- AFXTASKSPANE/CMFCTasksPaneTask::m_nWindowHeight
- AFXTASKSPANE/CMFCTasksPaneTask::m_pGroup
- AFXTASKSPANE/CMFCTasksPaneTask::m_rect
- AFXTASKSPANE/CMFCTasksPaneTask::m_strName
- AFXTASKSPANE/CMFCTasksPaneTask::m_uiCommandID
dev_langs:
- C++
helpviewer_keywords:
- CMFCTasksPaneTask class
ms.assetid: c5a7513b-cd8f-4e2e-b16f-650e1fe30954
caps.latest.revision: 27
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 20713b45c4b6aadc5cdfeaadb6ed269aaf7b337f
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctaskspanetask-class"></a>Cmfctaskspanetask-Klasse
Die `CMFCTasksPaneTask` Klasse ist eine Hilfsklasse, die Aufgaben für das Steuerelement für den Aufgabenbereich darstellt ( [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)). Das Task-Objekt stellt ein Element in der Aufgabengruppe ( [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)). Jede Aufgabe kann über einen Befehl verfügen, den das Framework ausführt, wenn ein Benutzer auf die Aufgabe klickt, und über ein Symbol, das auf der linken Seite des Aufgabennamens angezeigt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCTasksPaneTask : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCTasksPaneTask::CMFCTasksPaneTask](#cmfctaskspanetask)|Erstellt und initialisiert ein `CMFCTasksPaneTask` Objekt.|  
|`CMFCTasksPaneTask::~CMFCTasksPaneTask`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCTasksPaneTask::SetACCData](#setaccdata)|Bestimmt die Eingabehilfen-Daten für den aktuellen Vorgang.|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCTasksPaneTask::m_bAutoDestroyWindow](#m_bautodestroywindow)|Bestimmt, ob das Aufgabenfenster automatisch zerstört wird.|  
|[CMFCTasksPaneTask::m_bIsBold](#m_bisbold)|Bestimmt, ob das Framework eine Task-Bezeichnung in fett formatiertem Text zeichnet.|  
|[CMFCTasksPaneTask::m_dwUserData](#m_dwuserdata)|Enthält benutzerdefinierte Daten, die das Framework die Aufgabe zuordnet. Auf NULL festgelegt, wenn der Vorgang keine Daten zugeordneten hat.|  
|[CMFCTasksPaneTask::m_hwndTask](#m_hwndtask)|Ein Handle für das Fenster "Task".|  
|[CMFCTasksPaneTask::m_nIcon](#m_nicon)|Der Index in der Bildliste des Bilds, das vom Framework neben dem Task angezeigt wird.|  
|[CMFCTasksPaneTask::m_nWindowHeight](#m_nwindowheight)|Die Höhe des Fensters Aufgabe. Wenn der Vorgang keine Aufgabenfenster hat, ist dieser Wert&0; (null).|  
|[CMFCTasksPaneTask::m_pGroup](#m_pgroup)|Ein Zeiger auf die `CMFCTasksPaneTaskGroup` , zu der diese Aufgabe gehört.|  
|[CMFCTasksPaneTask::m_rect](#m_rect)|Gibt das umschließende Rechteck des Tasks an.|  
|[CMFCTasksPaneTask::m_strName](#m_strname)|Der Name des Vorgangs.|  
|[CMFCTasksPaneTask::m_uiCommandID](#m_uicommandid)|Gibt die Befehls-ID des Befehls, der das Framework ausführt, wenn der Benutzer klickt. Wenn dieser Wert nicht um eine gültige Befehls-ID ist, wird die Aufgabe als ein einfacher Bezeichner behandelt.|  
  
## <a name="remarks"></a>Hinweise  
 Die folgende Abbildung zeigt eine Aufgabengruppe, die drei Aufgaben enthält:  
  
 ![Aufgabengruppe, erweitert](../../mfc/reference/media/nexttaskgrpexpand.png "Nexttaskgrpexpand")  
  
> [!NOTE]
>  Wenn eine Aufgabe nicht über eine gültige Befehls-ID verfügt, wird es als ein einfacher Bezeichner behandelt.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxTasksPane.h  
  
##  <a name="cmfctaskspanetask"></a>CMFCTasksPaneTask::CMFCTasksPaneTask  
 Erstellt und initialisiert ein `CMFCTasksPaneTask` Objekt.  
  
```  
CMFCTasksPaneTask(
    CMFCTasksPaneTaskGroup* pGroup,  
    LPCTSTR lpszName,  
    int nIcon,  
    UINT uiCommandID,  
    DWORD dwUserData = 0,  
    HWND hwndTask = NULL,  
    BOOL bAutoDestroyWindow = FALSE,  
    int nWindowHeight = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `pGroup`  
 Gibt die [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) zu dem die Aufgabe gehört.  
  
 `lpszName`  
 Gibt den Namen des Tasks.  
  
 `nIcon`  
 Gibt den Index des Bilds für die Aufgabe in der Bildliste an.  
  
 `uiCommandID`  
 Gibt die Befehls-ID des Befehls, der beim Klicken auf die Aufgabe ausgeführt wird.  
  
 `dwUserData`  
 Benutzerdefinierte Daten.  
  
 `hwndTask`  
 Gibt das Handle für das Aufgabenfenster an.  
  
 `bAutoDestroyWindow`  
 Wenn `TRUE`, das Aufgabenfenster werden automatisch gelöscht.  
  
 `nWindowHeight`  
 Gibt die Höhe des Fensters Aufgabe.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_bautodestroywindow"></a>CMFCTasksPaneTask::m_bAutoDestroyWindow  
 Bestimmt, ob das Aufgabenfenster automatisch zerstört wird.  
  
```  
BOOL m_bAutoDestroyWindow;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie auf `TRUE` angeben, dass das Aufgabenfenster ( [CMFCTasksPaneTask::m_hwndTask](#m_hwndtask)) gelöscht werden soll, automatisch, andernfalls `FALSE`.  
  
##  <a name="m_bisbold"></a>CMFCTasksPaneTask::m_bIsBold  
 Bestimmt, ob eine Task-Bezeichnung in fett formatiertem Text gezeichnet wird.  
  
```  
BOOL m_bIsBold;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie dieses Element auf `TRUE` fett formatierten Text für die Task-Bezeichnung angezeigt.  
  
##  <a name="m_dwuserdata"></a>CMFCTasksPaneTask::m_dwUserData  
 Benutzerdefinierte Daten enthält, die der Aufgabe zugeordnet ist. Auf NULL festgelegt, wenn keine Daten der Aufgabe zugeordnet ist.  
  
```  
DWORD m_dwUserData;  
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_hwndtask"></a>CMFCTasksPaneTask::m_hwndTask  
 Ein Handle für das Fenster "Task".  
  
```  
HWND m_hwndTask;  
```  
  
### <a name="remarks"></a>Hinweise  
 Um ein Taskfenster hinzuzufügen, rufen Sie [CMFCTasksPane::AddWindow](../../mfc/reference/cmfctaskspane-class.md#addwindow).  
  
##  <a name="m_nicon"></a>CMFCTasksPaneTask::m_nIcon  
 Die Indexposition in einer Bildliste, die ein Abbild identifiziert, der neben dem angegebenen Task angezeigt wird.  
  
```  
int m_nIcon;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Bildliste wird festgelegt, indem [CMFCTasksPane::SetIconsList](../../mfc/reference/cmfctaskspane-class.md#seticonslist).  
  
 Legen Sie `m_nIcon` auf-1 festgelegt, wenn die Aufgabe ohne Bild angezeigt werden soll.  
  
##  <a name="m_nwindowheight"></a>CMFCTasksPaneTask::m_nWindowHeight  
 Die Höhe des Fensters Aufgabe. Wenn der Vorgang keine Aufgabenfenster hat, ist dieser Wert&0; (null).  
  
```  
int m_nWindowHeight;  
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_pgroup"></a>CMFCTasksPaneTask::m_pGroup  
 Zeiger auf die [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) zu der diese Aufgabe gehört.  
  
```  
CMFCTasksPaneTaskGroup* m_pGroup;  
```  
  
### <a name="remarks"></a>Hinweise  
 Jeder Vorgang muss eine übergeordnete Gruppe besitzen. Hinzufügen von Gruppen zu einem Aufgabenbereich durch den Aufruf [cmfctaskspane:: addgroup](../../mfc/reference/cmfctaskspane-class.md#addgroup).  
  
##  <a name="m_rect"></a>CMFCTasksPaneTask::m_rect  
 Gibt das umschließende Rechteck des Tasks an.  
  
```  
CRect m_rect;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert wird vom Framework berechnet, wenn die Aufgabe gezeichnet wird.  
  
##  <a name="m_strname"></a>CMFCTasksPaneTask::m_strName  
 Der Name des Vorgangs.  
  
```  
CString m_strName;  
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_uicommandid"></a>CMFCTasksPaneTask::m_uiCommandID  
 Gibt die Befehls-ID des Befehls, der ausgeführt wird, wenn der Benutzer klickt. Wenn dieser Wert nicht um eine gültige Befehls-ID ist, wird die Aufgabe als ein einfacher Bezeichner behandelt.  
  
```  
UINT m_uiCommandID;  
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setaccdata"></a>CMFCTasksPaneTask::SetACCData  
 Bestimmt die Eingabehilfen-Daten für den aktuellen Vorgang.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pParent`  
 Stellt das übergeordnete Fenster der aktuellen Aufgabe.  
  
 [out] `data`  
 Ein Objekt vom Typ `CAccessibilityData` , die mit den Zugriff auf Daten der aktuellen Aufgabe aufgefüllt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die `data` Parameter wurde erfolgreich mit den Zugriff auf Daten der aktuellen Aufgabe ausgefüllt, andernfalls `FALSE`.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)

