---
title: CWndClassInfo-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CWndClassInfo
- ATLWIN/ATL::CWndClassInfo
- ATLWIN/ATL::Register
- ATLWIN/ATL::m_atom
- ATLWIN/ATL::m_bSystemCursor
- ATLWIN/ATL::m_lpszCursorID
- ATLWIN/ATL::m_lpszOrigName
- ATLWIN/ATL::m_szAutoName
- ATLWIN/ATL::m_wc
- ATLWIN/ATL::pWndProc
dev_langs:
- C++
helpviewer_keywords:
- CWndClassInfo class
ms.assetid: c36fe7e1-75f1-4cf5-a06f-9f59c43fe6fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 11f61e89ab888b678bf54f65b999c0fd4394dbea
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43201661"
---
# <a name="cwndclassinfo-class"></a>CWndClassInfo-Klasse
Diese Klasse stellt Methoden zum Erfassen von Informationen für eine Fensterklasse.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```
class CWndClassInfo
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|[Registrieren](#register)|Registriert die Fensterklasse.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[m_atom](#m_atom)|Zur eindeutigen Identifizierung die registrierten Fensterklasse.|  
|[m_bSystemCursor](#m_bsystemcursor)|Gibt an, ob der Cursor-Ressource auf einen Systemcursor oder ein Cursor in eine Modulressource bezieht.|  
|[m_lpszCursorID](#m_lpszcursorid)|Gibt den Namen der Cursorressource an.|  
|[m_lpszOrigName](#m_lpszorigname)|Enthält den Namen einer vorhandenen Fenster-Klasse.|  
|[m_szAutoName](#m_szautoname)|Enthält den Namen einer ATL generierte der Fensterklasse.|  
|[m_wc](#m_wc)|Verwaltet die fensterklasseninformationen in einem `WNDCLASSEX` Struktur.|  
|[pWndProc](#pwndproc)|Zeigt auf die Fensterprozedur des eine vorhandene Fensterklasse.|  
  
## <a name="remarks"></a>Hinweise  
 `CWndClassInfo` verwaltet die Informationen des eine Fensterklasse. In der Regel `CWndClassInfo` über eine der drei Makros, DECLARE_WND_CLASS, DECLARE_WND_CLASS_EX oder DECLARE_WND_SUPERCLASS, wie in der folgenden Tabelle beschrieben:  
  
|Makro|Beschreibung|  
|-----------|-----------------|  
|[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)|`CWndClassInfo` registriert Informationen für eine neue Windows-Klasse.|  
|[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)|`CWndClassInfo` registriert Informationen für eine neue Windows-Klasse, einschließlich der Parameter für die Klasse.|  
|[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)|`CWndClassInfo` registriert Informationen für eine Fensterklasse, die auf einer vorhandenen Klasse basiert, aber verwendet eine andere Fensterprozedur. Dieses Verfahren wird die Erstellung einer übergeordneten Klasse bezeichnet.|  
  
 In der Standardeinstellung [CWindowImpl](../../atl/reference/cwindowimpl-class.md) enthält die `DECLARE_WND_CLASS` Makro beim Erstellen eines Fensters auf der Grundlage von einer neue Windows-Klasse. DECLARE_WND_CLASS werden die Standardstile und Hintergrundfarbe für das Steuerelement bereitstellt. Wenn Sie geben das Format an und Hintergrundfarbe selbst festlegen möchten, leiten Sie eine Klasse von `CWindowImpl` und das DECLARE_WND_CLASS_EX-Makro in der Klassendefinition enthalten.  
  
 Wenn Sie ein Fenster, die basierend auf eine vorhandene Fensterklasse erstellen möchten, leiten Sie Ihre Klasse von `CWindowImpl` und das DECLARE_WND_SUPERCLASS-Makro in der Klassendefinition enthalten. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwndclassinfo-class_1.h)]  
  
 Weitere Informationen zu Klassen, finden Sie unter [Fensterklassen](https://msdn.microsoft.com/library/windows/desktop/ms632596) im Windows SDK.  
  
 Weitere Informationen zum Verwenden von Fenstern in ATL finden Sie im Artikel [ATL-Fensterklassen](../../atl/atl-window-classes.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  
  
##  <a name="m_atom"></a>  CWndClassInfo::m_atom  
 Enthält den eindeutigen Bezeichner für die registrierten Fensterklasse.  
  
```
ATOM m_atom;
```  
  
##  <a name="m_bsystemcursor"></a>  CWndClassInfo::m_bSystemCursor  
 Bei "true", wird die Cursor Systemressource geladen werden, wenn die Fensterklasse registriert ist.  
  
```
BOOL m_bSystemCursor;
```  
  
### <a name="remarks"></a>Hinweise  
 Andernfalls wird der Cursor-Ressource, die im Modul enthalten geladen werden.  
  
 `CWndClassInfo` verwendet `m_bSystemCursor` nur, wenn die [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (die Standardeinstellung in [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) oder die [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) Makro angegeben ist. In diesem Fall `m_bSystemCursor` auf "true" initialisiert wird. Weitere Informationen finden Sie unter den [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) Übersicht.  
  
##  <a name="m_lpszcursorid"></a>  CWndClassInfo::m_lpszCursorID  
 Gibt an, entweder der Name der Cursorressource oder den Ressourcenbezeichner in das niederwertige Wort und 0 (null), das höherwertige Wort.  
  
```
LPCTSTR m_lpszCursorID;
```  
  
### <a name="remarks"></a>Hinweise  
 Bei der Registrierung der Fensterklasse, das Handle für das identifizierte Cursor `m_lpszCursorID` abgerufen und gespeichert werden, indem [M_wc](#m_wc).  
  
 `CWndClassInfo` verwendet `m_lpszCursorID` nur, wenn die [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (die Standardeinstellung in [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) oder die [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) Makro angegeben ist. In diesem Fall `m_lpszCursorID` mit IDC_ARROW initialisiert wird. Weitere Informationen finden Sie unter den [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) Übersicht.  
  
##  <a name="m_lpszorigname"></a>  CWndClassInfo::m_lpszOrigName  
 Enthält den Namen einer vorhandenen Fenster-Klasse.  
  
```
LPCTSTR m_lpszOrigName;
```  
  
### <a name="remarks"></a>Hinweise  
 `CWndClassInfo` verwendet `m_lpszOrigName` nur wenn enthalten die [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) Makro in der Klassendefinition. In diesem Fall `CWndClassInfo` eine Fensterklasse auf der Grundlage von der Klasse, die mit dem Namen von Registern `m_lpszOrigName`. Weitere Informationen finden Sie unter den [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) Übersicht.  
  
##  <a name="m_szautoname"></a>  CWndClassInfo::m_szAutoName  
 Enthält den Namen der Fensterklasse.  
  
```
TCHAR m_szAutoName[13];
```  
  
### <a name="remarks"></a>Hinweise  
 `CWndClassInfo` verwendet `m_szAutoName` nur dann, wenn NULL, um übergeben wird die `WndClassName` Parameter [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class), [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) oder [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) . ATL wird einen Namen zu erstellen, wenn die Fensterklasse registriert ist.  
  
##  <a name="m_wc"></a>  CWndClassInfo::m_wc  
 Verwaltet die fensterklasseninformationen in einem [WNDCLASSEX](https://msdn.microsoft.com/library/windows/desktop/ms633577) Struktur.  
  
```
WNDCLASSEX m_wc;
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie angegeben haben die [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (die Standardeinstellung in [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) oder die [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) -Makro, `m_wc` enthält Informationen zu einer neue Windows-Klasse.  
  
 Wenn Sie angegeben haben die [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) Makro `m_wc` enthält Informationen zu einer übergeordneten Klasse – eine Fensterklasse, die auf einer vorhandenen Klasse basiert, aber verwendet eine andere Fensterprozedur. [M_lpszOrigName](#m_lpszorigname) und [pWndProc](#pwndproc) speichern Sie die vorhandene Fensterklasse-Namen und die Fensterprozedur.  
  
##  <a name="pwndproc"></a>  CWndClassInfo::pWndProc  
 Zeigt auf die Fensterprozedur des eine vorhandene Fensterklasse.  
  
```
WNDPROC pWndProc;
```  
  
### <a name="remarks"></a>Hinweise  
 `CWndClassInfo` verwendet `pWndProc` nur wenn enthalten die [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) Makro in der Klassendefinition. In diesem Fall `CWndClassInfo` eine Fensterklasse, die auf einer vorhandenen Klasse basiert, aber verwendet eine anderes Fensterprozedur registriert. Die vorhandene Fensterklasse Fensterprozedur wird gespeichert, `pWndProc`. Weitere Informationen finden Sie unter den [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) Übersicht.  
  
##  <a name="register"></a>  CWndClassInfo::Register  
 Wird aufgerufen, indem [CWindowImpl:: Create](../../atl/reference/cwindowimpl-class.md#create) Fensterklasse registrieren, wenn er noch nicht registriert wurde.  
  
```
ATOM Register(WNDPROC* pProc);
```  
  
### <a name="parameters"></a>Parameter  
 *pProc*  
 [out] Gibt die ursprüngliche Fensterprozedur der eine vorhandene Fensterklasse an.  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg wird ein Atom, die eindeutig identifiziert die Fensterklasse registriert wird. Andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie angegeben haben die [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (die Standardeinstellung für [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) oder die [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) Makro `Register` registriert eine neue Windows-Klasse. In diesem Fall die *pProc* Parameter wird nicht verwendet.  
  
 Wenn Sie angegeben haben die [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) Makro `Register` registriert eine übergeordnete Klasse – eine Fensterklasse, die auf einer vorhandenen Klasse basiert, aber verwendet eine andere Fensterprozedur. In die vorhandene Fensterklasse Fensterprozedur zurückgegeben *pProc*.  
  
## <a name="see-also"></a>Siehe auch  
 [CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)