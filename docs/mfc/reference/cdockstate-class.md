---
title: Klasse CDockState | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockState
dev_langs:
- C++
helpviewer_keywords:
- dock state
- size
- docking control bars
- CDockState class
- states, dockable control bar
- position, control bar
- size, control bar
- docking tool windows
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: fc8beb80cc35c1816fbc305ece2bfbc5df2e7cd0
ms.lasthandoff: 02/24/2017

---
# <a name="cdockstate-class"></a>CDockState-Klasse
Eine serialisierte `CObject` -Klasse, die den Zustand einer oder mehrerer andockbarer Steuerleisten in einem persistenten Speicher (eine Datei) lädt, entlädt oder löscht.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDockState : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDockState::Clear](#clear)|Löscht die Zustandsinformationen andocken.|  
|[CDockState::GetVersion](#getversion)|Ruft die Versionsnummer des gespeicherten Status Leiste.|  
|[CDockState::LoadState](#loadstate)|Ruft Statusinformationen aus der Registrierung oder. INI-Datei.|  
|[CDockState::SaveState](#savestate)|Speichert Zustandsinformationen der Registrierung oder der INI-Datei.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDockState::m_arrBarInfo](#m_arrbarinfo)|Array von Zeigern auf den gespeicherten Andocken Zustandsinformationen mit einem Eintrag für jede Steuerleiste.|  
  
## <a name="remarks"></a>Hinweise  
 Das Andocken beinhaltet die Größe und Position der Leiste und davon, ob es angedockt ist. Beim Abrufen der gespeicherte Zustand Andocken `CDockState` überprüft der Leiste Position und, wenn die Statusleiste nicht mit den aktuellen Bildschirm Einstellungen angezeigt wird `CDockState` skaliert des Balkens positionieren, sodass es sichtbar ist. Der Hauptzweck der `CDockState` besteht darin, den gesamten Status einer Anzahl von Steuerleisten zu halten und zu diesem Zustand gespeichert werden und entweder in der Registrierungs, die Anwendung geladen. INI-Datei oder in binärer Form als Teil einer `CArchive` Inhalt des Objekts.  
  
 Die Leiste kann alle andockbaren Balken-, z. B. eine Symbolleiste, eine Statusleiste oder eine Dialogleiste. `CDockState`Objekte sind geschrieben und gelesen werden, oder aus einer Datei über ein `CArchive` Objekt.  
  
 [CFrameWnd::GetDockState](../../mfc/reference/cframewnd-class.md#getdockstate) Ruft Informationen über den Zustand von allen des Rahmenfensters `CControlBar` Objekte und fügt es in die `CDockState` Objekt. Anschließend können Sie schreiben den Inhalt der `CDockState` Objekt Speicher mit [Serialize](../../mfc/reference/cobject-class.md#serialize) oder [CDockState::SaveState](#savestate). Wenn Sie später den Status der Steuerleisten Rahmenfenster wiederherstellen möchten, können Sie den Status mit laden `Serialize` oder [CDockState::LoadState](#loadstate), dann [CFrameWnd::SetDockState](../../mfc/reference/cframewnd-class.md#setdockstate) den gespeicherten Zustand das Rahmenfenster Steuerleisten anwenden.  
  
 Weitere Informationen zum Andocken Steuerleisten, finden Sie in den Artikeln [Steuerleisten](../../mfc/control-bars.md), [Symbolleisten: andockbare und unverankerte](../../mfc/docking-and-floating-toolbars.md), und [Rahmenfenster](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CDockState`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxadv.h  
  
##  <a name="a-namecleara--cdockstateclear"></a><a name="clear"></a>CDockState::Clear  
 Rufen Sie diese Funktion deaktivieren Sie alle andockbaren Informationen aus der `CDockState` Objekt.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Hinweise  
 Dies schließt nicht nur, ob die Leiste oder nicht, aber die Größe und Position des Balkens angedockt ist und ob es angezeigt wird.  
  
##  <a name="a-namegetversiona--cdockstategetversion"></a><a name="getversion"></a>CDockState::GetVersion  
 Rufen Sie diese Funktion zum Abrufen der Versionsnummer des gespeicherten Status Leiste.  
  
```  
DWORD GetVersion();
```  
  
### <a name="return-value"></a>Rückgabewert  
 1, wenn die Leiste gespeicherten Informationen ist älter als die aktuelle Balken Zustand. 2, wenn die Leiste gespeicherten Informationen sind die gleichen wie die aktuelle Leiste Zustand.  
  
### <a name="remarks"></a>Hinweise  
 Versionsunterstützung ermöglicht eine überarbeitete angezeigt, die noch in der Lage zu erkennen und Laden des persistenten Status erstellt, die von einer früheren Version des Balkens und neue persistente Eigenschaften hinzufügen.  
  
##  <a name="a-nameloadstatea--cdockstateloadstate"></a><a name="loadstate"></a>CDockState::LoadState  
 Rufen Sie diese Funktion zum Abrufen von Informationen aus der Registrierung oder. INI-Datei.  
  
```  
void LoadState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszProfileName`  
 Zeigt auf eine Null-Teminated-Zeichenfolge, die den Namen eines Abschnitts in der Initialisierungsdatei oder einen Schlüssel in der Windows-Registrierung, der Speicherort der Zustandsinformationen angibt.  
  
### <a name="remarks"></a>Hinweise  
 Der Profilname ist der Teil der Anwendungsverzeichnis ist. INI-Datei oder der Registrierung, die die Balken Zustandsinformationen enthält. Sie können die Steuerleiste Zustandsinformationen speichern, in der Registrierung oder. INI-Datei mit `SaveState`.  
  
##  <a name="a-namemarrbarinfoa--cdockstatemarrbarinfo"></a><a name="m_arrbarinfo"></a>CDockState::m_arrBarInfo  
 Ein `CPtrArray` -Objekt, das ein Array von Zeigern auf die gespeicherten Informationen zum Balken für jede Steuerleiste handelt, die Statusinformationen im gespeichert hat die `CDockState` Objekt.  
  
```  
CPtrArray m_arrBarInfo;  
```  
  
##  <a name="a-namesavestatea--cdockstatesavestate"></a><a name="savestate"></a>CDockState::SaveState  
 Mit dieser Funktion können Sie die Statusinformationen in der Registrierung speichern oder. INI-Datei.  
  
```  
void SaveState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszProfileName`  
 Zeigt auf eine Null-Teminated-Zeichenfolge, die den Namen eines Abschnitts in der Initialisierungsdatei oder einen Schlüssel in der Windows-Registrierung, der Speicherort der Zustandsinformationen angibt.  
  
### <a name="remarks"></a>Hinweise  
 Der Profilname ist der Teil der Anwendungsverzeichnis ist. INI-Datei oder der Registrierung enthält, die Statusinformationen der Steuerleiste. `SaveState`speichert auch die aktuelle Größe des Bildschirms. Sie können Steuerelementinformationen aus der Registrierung abrufen oder. INI-Datei mit `LoadState`.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)


