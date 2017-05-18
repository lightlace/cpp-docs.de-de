---
title: CWndClassInfo Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 22
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 071a6683a459c1b668cfa3eb5e866b461d82ab29
ms.contentlocale: de-de
ms.lasthandoff: 03/31/2017

---
# <a name="cwndclassinfo-class"></a>CWndClassInfo-Klasse
Diese Klasse stellt Methoden zum Erfassen von Informationen für eine Fensterklasse.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CWndClassInfo
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|[Registrieren](#register)|Registriert die Fensterklasse.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[m_atom](#m_atom)|Zur eindeutigen Identifizierung der registrierten Fensterklasse.|  
|[m_bSystemCursor](#m_bsystemcursor)|Gibt an, ob der Cursor-Ressource auf einen Systemcursor oder ein Cursor in einem Modul Ressource verweist.|  
|[m_lpszCursorID](#m_lpszcursorid)|Gibt den Namen der Cursorressource.|  
|[m_lpszOrigName](#m_lpszorigname)|Enthält den Namen einer vorhandenen Fenster-Klasse.|  
|[m_szAutoName](#m_szautoname)|Enthält eine ATL generierter Name der Fensterklasse.|  
|[m_wc](#m_wc)|Verwaltet die fensterklasseninformationen in einem **WNDCLASSEX** Struktur.|  
|[pWndProc](#pwndproc)|Verweist auf die Fensterprozedur für eine vorhandene Fensterklasse überordnen.|  
  
## <a name="remarks"></a>Hinweise  
 `CWndClassInfo`verwaltet die Informationen des eine Fensterklasse. In der Regel `CWndClassInfo` über einen der drei Makros `DECLARE_WND_CLASS`, `DECLARE_WND_CLASS_EX`, oder `DECLARE_WND_SUPERCLASS`, wie in der folgenden Tabelle beschrieben:  
  
|Makro|Beschreibung|  
|-----------|-----------------|  
|[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)|`CWndClassInfo`Informationen für eine neue Fensterklasse registriert.|  
|[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)|`CWndClassInfo`Informationen für eine neue Windows-Klasse, einschließlich der Parameter für die Klasse registriert.|  
|[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)|`CWndClassInfo`Informationen für eine Fensterklasse, die auf einer vorhandenen Klasse basiert, aber verwendet eine anderes Zeitfenster Prozedur registriert. Diese Technik wird das Erstellen von übergeordneten Klassen bezeichnet.|  
  
 Standardmäßig [CWindowImpl](../../atl/reference/cwindowimpl-class.md) enthält die `DECLARE_WND_CLASS` Makro beim Erstellen eines Fensters basierend auf einem neuen Fensterklasse. DECLARE_WND_CLASS bietet Standardstile und Hintergrundfarbe für das Steuerelement. Wenn Sie gibt den Stil und Hintergrundfarbe selbst festlegen möchten, leiten Sie eine Klasse von `CWindowImpl` und enthalten die `DECLARE_WND_CLASS_EX` Makros in der Klasse.  
  
 Wenn Sie beim Erstellen eines Fensters basierend auf eine vorhandene Fensterklasse überordnen möchten, leiten Sie eine Klasse von `CWindowImpl` und enthalten die `DECLARE_WND_SUPERCLASS` Makros in der Klasse. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_Windowing #43](../../atl/codesnippet/cpp/cwndclassinfo-class_1.h)]  
  
 Weitere Informationen zu Fensterklassen, finden Sie unter [Fensterklassen](http://msdn.microsoft.com/library/windows/desktop/ms632596) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zum Verwenden von Fenstern in ATL finden Sie im Artikel [ATL-Fensterklassen](../../atl/atl-window-classes.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  
  
##  <a name="m_atom"></a>CWndClassInfo::m_atom  
 Enthält den eindeutigen Bezeichner für die registrierten Fensterklasse.  
  
```
ATOM m_atom;
```  
  
##  <a name="m_bsystemcursor"></a>CWndClassInfo::m_bSystemCursor  
 Wenn **"true"**, die Systemressource Cursor wird geladen werden, wenn die Fensterklasse registriert ist.  
  
```
BOOL m_bSystemCursor;
```  
  
### <a name="remarks"></a>Hinweise  
 Andernfalls wird die Cursorressource, die in Ihrem Modul enthalten geladen werden.  
  
 `CWndClassInfo`verwendet `m_bSystemCursor` nur, wenn die [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (die Standardeinstellung in [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) oder die [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) Makro angegeben ist. In diesem Fall `m_bSystemCursor` wird mit initialisiert **"true"**. Weitere Informationen finden Sie unter der [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) (Übersicht).  
  
##  <a name="m_lpszcursorid"></a>CWndClassInfo::m_lpszCursorID  
 Gibt entweder den Namen der Cursorressource oder den Ressourcenbezeichner in das niederwertige Wort und 0 (null), in das höherwertige Wort an.  
  
```
LPCTSTR m_lpszCursorID;
```  
  
### <a name="remarks"></a>Hinweise  
 Wann die Fensterklasse registriert wird, das Handle für die identifizierte Cursor `m_lpszCursorID` abgerufen und gespeichert werden, indem [M_wc](#m_wc).  
  
 `CWndClassInfo`verwendet `m_lpszCursorID` nur, wenn die [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (die Standardeinstellung in [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) oder die [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) Makro angegeben ist. In diesem Fall `m_lpszCursorID` wird mit initialisiert **IDC_ARROW**. Weitere Informationen finden Sie unter der [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) (Übersicht).  
  
##  <a name="m_lpszorigname"></a>CWndClassInfo::m_lpszOrigName  
 Enthält den Namen einer vorhandenen Fenster-Klasse.  
  
```
LPCTSTR m_lpszOrigName;
```  
  
### <a name="remarks"></a>Hinweise  
 `CWndClassInfo`verwendet `m_lpszOrigName` nur beim Schließen der [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) Makros in der Klasse. In diesem Fall `CWndClassInfo` eine Fensterklasse auf der Klasse mit dem Namen basierend von Registern `m_lpszOrigName`. Weitere Informationen finden Sie unter der [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) (Übersicht).  
  
##  <a name="m_szautoname"></a>CWndClassInfo::m_szAutoName  
 Enthält den Namen der Fensterklasse.  
  
```
TCHAR m_szAutoName[13];
```  
  
### <a name="remarks"></a>Hinweise  
 `CWndClassInfo`verwendet `m_szAutoName` nur, wenn **NULL** übergeben wird, für die `WndClassName` Parameter [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class), [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) oder [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass). ATL wird ein Name erstellt, bei der die Fensterklasse registriert ist.  
  
##  <a name="m_wc"></a>CWndClassInfo::m_wc  
 Verwaltet die fensterklasseninformationen in einem [WNDCLASSEX](http://msdn.microsoft.com/library/windows/desktop/ms633577) Struktur.  
  
```
WNDCLASSEX m_wc;
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie angegeben haben die [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (die Standardeinstellung in [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) oder die [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) -Makro, `m_wc` enthält Informationen über eine neue Windows-Klasse.  
  
 Wenn Sie angegeben haben die [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) Makro `m_wc` enthält Informationen zu einer übergeordneten Klasse – eine Fensterklasse, die auf einer vorhandenen Klasse basiert, aber verwendet eine anderes Zeitfenster-Prozedur. [M_lpszOrigName](#m_lpszorigname) und [pWndProc](#pwndproc) speichern Sie die vorhandene Fensterklasse überordnen Name und Fensterprozedur,.  
  
##  <a name="pwndproc"></a>CWndClassInfo::pWndProc  
 Verweist auf die Fensterprozedur für eine vorhandene Fensterklasse überordnen.  
  
```
WNDPROC pWndProc;
```  
  
### <a name="remarks"></a>Hinweise  
 `CWndClassInfo`verwendet `pWndProc` nur beim Schließen der [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) Makros in der Klasse. In diesem Fall `CWndClassInfo` eine Fensterklasse, die auf einer vorhandenen Klasse basiert, aber verwendet eine anderes Zeitfenster Prozedur registriert. Die vorhandene Fensterklasse überordnen Fensterprozedur wird gespeichert, `pWndProc`. Weitere Informationen finden Sie unter der [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) (Übersicht).  
  
##  <a name="register"></a>CWndClassInfo::Register  
 Wird aufgerufen, indem [CWindowImpl:: Create](../../atl/reference/cwindowimpl-class.md#create) Fensterklasse zu registrieren, wenn er noch nicht registriert wurde.  
  
```
ATOM Register(WNDPROC* pProc);
```  
  
### <a name="parameters"></a>Parameter  
 `pProc`  
 [out] Gibt die ursprüngliche Fensterprozedur der eine vorhandene Fensterklasse überordnen an.  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg ein Atom, identifiziert eindeutig die Fensterklasse registriert wird. Andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie angegeben haben die [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (die Standardeinstellung in [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) oder die [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) -Makro, `Register` eine neue Fensterklasse registriert. In diesem Fall die `pProc` Parameter wird nicht verwendet.  
  
 Wenn Sie angegeben haben die [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) -Makro, `Register` eine übergeordneten Klasse registriert – eine Fensterklasse, die auf einer vorhandenen Klasse basiert, aber verwendet eine anderes Zeitfenster-Prozedur. Die vorhandene Fensterklasse überordnen Fensterprozedur wird zurückgegeben, `pProc`.  
  
## <a name="see-also"></a>Siehe auch  
 [CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
