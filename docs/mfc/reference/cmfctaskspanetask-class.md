---
title: CMFCTasksPaneTask-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CMFCTasksPaneTask [MFC], CMFCTasksPaneTask
- CMFCTasksPaneTask [MFC], SetACCData
- CMFCTasksPaneTask [MFC], m_bAutoDestroyWindow
- CMFCTasksPaneTask [MFC], m_bIsBold
- CMFCTasksPaneTask [MFC], m_dwUserData
- CMFCTasksPaneTask [MFC], m_hwndTask
- CMFCTasksPaneTask [MFC], m_nIcon
- CMFCTasksPaneTask [MFC], m_nWindowHeight
- CMFCTasksPaneTask [MFC], m_pGroup
- CMFCTasksPaneTask [MFC], m_rect
- CMFCTasksPaneTask [MFC], m_strName
- CMFCTasksPaneTask [MFC], m_uiCommandID
ms.assetid: c5a7513b-cd8f-4e2e-b16f-650e1fe30954
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 041a207af69ac65646e1b30672250b84aa3a5d36
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37853968"
---
# <a name="cmfctaskspanetask-class"></a>CMFCTasksPaneTask-Klasse
Die `CMFCTasksPaneTask` Klasse ist eine Hilfsklasse, die Aufgaben für das Aufgabenbereich-Steuerelement darstellt ( [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)). Das Aufgabenobjekt stellt ein Element in der Aufgabengruppe dar ( [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)). Jede Aufgabe kann über einen Befehl verfügen, den das Framework ausführt, wenn ein Benutzer auf die Aufgabe klickt, und über ein Symbol, das auf der linken Seite des Aufgabennamens angezeigt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCTasksPaneTask : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCTasksPaneTask::CMFCTasksPaneTask](#cmfctaskspanetask)|Erstellt und initialisiert ein `CMFCTasksPaneTask` Objekt.|  
|`CMFCTasksPaneTask::~CMFCTasksPaneTask`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCTasksPaneTask::SetACCData](#setaccdata)|Bestimmt die barrierefreiheitsdaten für die aktuelle Aufgabe an.|  
  
### <a name="data-members"></a>Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CMFCTasksPaneTask::m_bAutoDestroyWindow](#m_bautodestroywindow)|Bestimmt, ob das Aufgabenfenster automatisch zerstört wird.|  
|[CMFCTasksPaneTask::m_bIsBold](#m_bisbold)|Bestimmt, ob das Framework eine Task-Bezeichnung in fett formatiertem Text zeichnet.|  
|[CMFCTasksPaneTask::m_dwUserData](#m_dwuserdata)|Enthält benutzerdefinierte Daten, die das Framework die Aufgabe zuordnet. Auf 0 (null) festgelegt, wenn der Task keine zugeordneten Daten enthält.|  
|[CMFCTasksPaneTask::m_hwndTask](#m_hwndtask)|Ein Handle für das Aufgabenfenster.|  
|[CMFCTasksPaneTask::m_nIcon](#m_nicon)|Der Index in der Bildliste des Bilds, das das Framework neben dem Task zeigt.|  
|[CMFCTasksPaneTask::m_nWindowHeight](#m_nwindowheight)|Die Höhe des Fensters Aufgabe. Wenn der Vorgang keine Aufgabenfenster hat, ist dieser Wert 0 (null).|  
|[CMFCTasksPaneTask::m_pGroup](#m_pgroup)|Ein Zeiger auf die `CMFCTasksPaneTaskGroup` , zu der diese Aufgabe gehört.|  
|[CMFCTasksPaneTask::m_rect](#m_rect)|Gibt das umschließende Rechteck des Tasks an.|  
|[CMFCTasksPaneTask::m_strName](#m_strname)|Der Name der Aufgabe.|  
|[CMFCTasksPaneTask::m_uiCommandID](#m_uicommandid)|Gibt an, die Befehls-ID des Befehls, die das Framework ausgeführt wird, wenn der Benutzer klickt. Wenn dieser Wert nicht über eine gültige Befehls-ID ist, wird die Aufgabe als eine einfache Bezeichnung behandelt.|  
  
## <a name="remarks"></a>Hinweise  
 Die folgende Abbildung zeigt eine Aufgabengruppe, die drei Aufgaben enthält:  
  
 ![Aufgabengruppe, erweitert](../../mfc/reference/media/nexttaskgrpexpand.png "Nexttaskgrpexpand")  
  
> [!NOTE]
>  Wenn eine Aufgabe nicht über eine gültige Befehls-ID verfügt, wird es als einfache Bezeichnung behandelt.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxTasksPane.h  
  
##  <a name="cmfctaskspanetask"></a>  CMFCTasksPaneTask::CMFCTasksPaneTask  
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
 *pGroup*  
 Gibt an, die [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) zu dem der Task gehört.  
  
 *Wert*  
 Gibt den Namen der Aufgabe.  
  
 *nIcon*  
 Gibt den Index eines Bildes mit der Aufgabe in der Bildliste an.  
  
 *uiCommandID*  
 Gibt an, die Befehls-ID des Befehls, der beim Klicken auf die Aufgabe ausgeführt wird.  
  
 *dwUserData*  
 Mit benutzerdefinierten Daten.  
  
 *hwndTask*  
 Gibt das Handle für das Aufgabenfenster an.  
  
 *bAutoDestroyWindow*  
 Wenn TRUE, wird das Aufgabenfenster automatisch zerstört.  
  
 *nWindowHeight*  
 Gibt die Höhe des Fensters Aufgabe.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_bautodestroywindow"></a>  CMFCTasksPaneTask::m_bAutoDestroyWindow  
 Bestimmt, ob das Aufgabenfenster automatisch zerstört wird.  
  
```  
BOOL m_bAutoDestroyWindow;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie auf "true", um anzugeben, dass das Aufgabenfenster ( [CMFCTasksPaneTask::m_hwndTask](#m_hwndtask)) gelöscht werden soll, automatisch ist, andernfalls FALSE.  
  
##  <a name="m_bisbold"></a>  CMFCTasksPaneTask::m_bIsBold  
 Bestimmt, ob eine Task-Bezeichnung in fett formatiertem Text gezeichnet wird.  
  
```  
BOOL m_bIsBold;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie dieses Mitglied auf "true" Anzeige für die Task-Bezeichnung fett formatierten Text.  
  
##  <a name="m_dwuserdata"></a>  CMFCTasksPaneTask::m_dwUserData  
 Enthält den benutzerdefinierten Daten, die der Aufgabe zugeordnet ist. Auf 0 (null) festgelegt, wenn keine Daten der Aufgabe zugeordnet sind.  
  
```  
DWORD m_dwUserData;  
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_hwndtask"></a>  CMFCTasksPaneTask::m_hwndTask  
 Ein Handle für das Aufgabenfenster.  
  
```  
HWND m_hwndTask;  
```  
  
### <a name="remarks"></a>Hinweise  
 Um ein Aufgabenfenster hinzuzufügen, rufen [CMFCTasksPane::AddWindow](../../mfc/reference/cmfctaskspane-class.md#addwindow).  
  
##  <a name="m_nicon"></a>  CMFCTasksPaneTask::m_nIcon  
 Die Indexposition in einer Bildliste an, die ein Bild, das neben dem angegebenen Task angezeigt wird, identifiziert.  
  
```  
int m_nIcon;  
```  
  
### <a name="remarks"></a>Hinweise  
 Liste der Bilder wird festgelegt, indem [CMFCTasksPane::SetIconsList](../../mfc/reference/cmfctaskspane-class.md#seticonslist).  
  
 Legen Sie `m_nIcon` , 1, wenn die Aufgabe ohne Bild angezeigt werden soll.  
  
##  <a name="m_nwindowheight"></a>  CMFCTasksPaneTask::m_nWindowHeight  
 Die Höhe des Fensters Aufgabe. Wenn der Vorgang keine Aufgabenfenster hat, ist dieser Wert 0 (null).  
  
```  
int m_nWindowHeight;  
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_pgroup"></a>  CMFCTasksPaneTask::m_pGroup  
 Zeiger auf die [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) zu dem diese Aufgabe gehört.  
  
```  
CMFCTasksPaneTaskGroup* m_pGroup;  
```  
  
### <a name="remarks"></a>Hinweise  
 Jeder Aufgabe muss eine übergeordnete Gruppe haben. Sie können Gruppen zu einem Aufgabenbereich hinzufügen, durch den Aufruf [cmfctaskspane:: addgroup](../../mfc/reference/cmfctaskspane-class.md#addgroup).  
  
##  <a name="m_rect"></a>  CMFCTasksPaneTask::m_rect  
 Gibt das umschließende Rechteck des Tasks an.  
  
```  
CRect m_rect;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert wird vom Framework berechnet, wenn die Aufgabe gezeichnet wird.  
  
##  <a name="m_strname"></a>  CMFCTasksPaneTask::m_strName  
 Der Name der Aufgabe.  
  
```  
CString m_strName;  
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_uicommandid"></a>  CMFCTasksPaneTask::m_uiCommandID  
 Gibt an, die Befehls-ID des Befehls, der ausgeführt wird, wenn der Benutzer klickt. Wenn dieser Wert nicht über eine gültige Befehls-ID ist, wird die Aufgabe als eine einfache Bezeichnung behandelt.  
  
```  
UINT m_uiCommandID;  
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setaccdata"></a>  CMFCTasksPaneTask::SetACCData  
 Bestimmt die barrierefreiheitsdaten für die aktuelle Aufgabe an.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pParent*  
 Stellt das übergeordnete Fenster des die aktuelle Aufgabe dar.  
  
 [out] *Daten*  
 Ein Objekt des Typs `CAccessibilityData` , die mit den Zugriff auf Daten der aktuellen Aufgabe aufgefüllt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn die *Daten* Parameter wurde erfolgreich mit den Zugriff auf Daten der aktuellen Aufgabe ausgefüllt, andernfalls "false".  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)
