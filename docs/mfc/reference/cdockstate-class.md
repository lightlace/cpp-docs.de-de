---
title: CDockState Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockState
- AFXADV/CDockState
- AFXADV/CDockState::Clear
- AFXADV/CDockState::GetVersion
- AFXADV/CDockState::LoadState
- AFXADV/CDockState::SaveState
- AFXADV/CDockState::m_arrBarInfo
dev_langs:
- C++
helpviewer_keywords:
- CDockState [MFC], Clear
- CDockState [MFC], GetVersion
- CDockState [MFC], LoadState
- CDockState [MFC], SaveState
- CDockState [MFC], m_arrBarInfo
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6669f5a2b54c376e545b1ba6b9227d6137726256
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdockstate-class"></a>CDockState-Klasse
Eine serialisierte `CObject` -Klasse, die den Zustand einer oder mehrerer andockbarer Steuerleisten in einem persistenten Speicher (eine Datei) lädt, entlädt oder löscht.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDockState : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDockState::Clear](#clear)|Löscht die Zustandsinformationen andocken.|  
|[CDockState::GetVersion](#getversion)|Ruft die Versionsnummer des gespeicherten Status Leiste.|  
|[CDockState::LoadState](#loadstate)|Ruft die Zustandsinformationen aus der Registrierung oder. INI-Datei.|  
|[CDockState::SaveState](#savestate)|Speichert Zustandsinformationen der Registrierung oder der INI-Datei.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDockState::m_arrBarInfo](#m_arrbarinfo)|Array von Zeigern zu den gespeicherten Andocken Zustandsinformationen mit einem Eintrag für jede Steuerleiste.|  
  
## <a name="remarks"></a>Hinweise  
 Die Dock-Status umfasst die Größe und Position der Balken und davon, ob es angedockt wird. Beim Abrufen von den gespeicherten Zustand, Andocken `CDockState` überprüft der Leiste Position und, wenn die Statusleiste nicht mit den aktuellen Bildschirm Einstellungen sichtbar ist `CDockState` skaliert der Leiste positionieren, sodass es angezeigt wird. Die Hauptaufgabe `CDockState` besteht darin, den gesamten Status einer Anzahl von Steuerleisten aufzunehmen und zu diesem Zustand gespeichert werden sollen, und entweder in der Registrierungs, die Anwendung geladen. INI-Datei oder in binärer Form als Teil einer `CArchive` Inhalt des Objekts.  
  
 Die Leiste kann eine beliebige andockbaren Balken-, z. B. eine Symbolleiste, die Statusleiste oder die Dialogleiste sein. `CDockState`Objekte sind geschrieben und gelesen werden, oder aus einer Datei über eine `CArchive` Objekt.  
  
 [CFrameWnd::GetDockState](../../mfc/reference/cframewnd-class.md#getdockstate) Ruft die Statusinformationen alle des Rahmenfensters `CControlBar` -Objekte und fügt sie in der `CDockState` Objekt. Anschließend können Sie den Inhalt der Schreiben der `CDockState` Objekt in den Speicher mit [Serialize](../../mfc/reference/cobject-class.md#serialize) oder [CDockState::SaveState](#savestate). Wenn Sie später den Status der Steuerleisten im Rahmenfenster wiederherstellen möchten, können Sie den Status mit laden `Serialize` oder [CDockState::LoadState](#loadstate), verwenden Sie dann [CFrameWnd::SetDockState](../../mfc/reference/cframewnd-class.md#setdockstate) gespeicherten anwenden Zustand, der das Rahmenfenster Steuerleisten.  
  
 Weitere Informationen zum Andocken Steuerleisten, finden Sie in den Artikeln [Steuerleisten](../../mfc/control-bars.md), [Symbolleisten: andockbare und unverankerte](../../mfc/docking-and-floating-toolbars.md), und [Rahmenfenster](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDockState`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxadv.h  
  
##  <a name="clear"></a>CDockState::Clear  
 Mit dieser Funktion können Sie alle andockbaren in gespeicherten Informationen Deaktivieren der `CDockState` Objekt.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Hinweise  
 Dies schließt nicht nur, ob die Leiste oder nicht, aber die Leiste, Größe und Position angedockt ist und unabhängig davon, ob es angezeigt wird.  
  
##  <a name="getversion"></a>CDockState::GetVersion  
 Mit dieser Funktion wird zum Abrufen der Versionsnummer des gespeicherten Status Leiste.  
  
```  
DWORD GetVersion();
```  
  
### <a name="return-value"></a>Rückgabewert  
 1, wenn die gespeicherte Leiste Informationen ist älter als die aktuelle Strich Status; 2, wenn die Leiste gespeicherte Daten sind die gleichen wie die aktuelle Leiste Zustand.  
  
### <a name="remarks"></a>Hinweise  
 Versionsunterstützung ermöglicht einen überarbeiteten Balken weiterhin in der Lage zu ermitteln und Laden des persistenten Status, die von einer früheren Version des Balkens erstellt und neue persistente Eigenschaften hinzufügen.  
  
##  <a name="loadstate"></a>CDockState::LoadState  
 Mit dieser Funktion wird zum Abrufen von Statusinformationen aus der Registrierung oder. INI-Datei.  
  
```  
void LoadState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszProfileName`  
 Zeigt auf eine Null-Teminated-Zeichenfolge, die den Namen eines Abschnitts in der Initialisierungsdatei oder einen Schlüssel in der Windows-Registrierung, der Speicherort der Zustandsinformationen angibt.  
  
### <a name="remarks"></a>Hinweise  
 Der Profilname ist der Teil der Anwendungsverzeichnis. INI-Datei oder der Registrierung, die die Balken Zustandsinformationen enthält. Sie können die Steuerleiste Zustandsinformationen speichern, an der Registrierung oder. INI-Datei mit `SaveState`.  
  
##  <a name="m_arrbarinfo"></a>CDockState::m_arrBarInfo  
 Ein `CPtrArray` Objekt, das ein Array von Zeigern auf gespeicherte Leiste Steuerinformationen für jede Steuerleiste, die Statusinformationen im gespeichert wurde, ist die `CDockState` Objekt.  
  
```  
CPtrArray m_arrBarInfo;  
```  
  
##  <a name="savestate"></a>CDockState::SaveState  
 Mit dieser Funktion können Sie die Statusinformationen in der Registrierung zu speichern oder. INI-Datei.  
  
```  
void SaveState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszProfileName`  
 Zeigt auf eine Null-Teminated-Zeichenfolge, die den Namen eines Abschnitts in der Initialisierungsdatei oder einen Schlüssel in der Windows-Registrierung, der Speicherort der Zustandsinformationen angibt.  
  
### <a name="remarks"></a>Hinweise  
 Der Profilname ist der Teil der Anwendungsverzeichnis. INI-Datei oder die Registrierung enthält, die Statusinformationen der Steuerleiste. `SaveState`speichert auch die Größe des aktuellen Bildschirms aus. Sie können Informationen über die Leiste abrufen, aus der Registrierung oder. INI-Datei mit `LoadState`.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)

