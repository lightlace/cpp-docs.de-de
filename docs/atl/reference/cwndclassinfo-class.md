---
title: CWndClassInfo Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWndClassInfo
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
translationtype: Machine Translation
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: f036d79c7a9420e083eb86023c5cbf98906cc1cc
ms.lasthandoff: 02/24/2017

---
# <a name="cwndclassinfo-class"></a>CWndClassInfo-Klasse
Diese Klasse stellt Methoden zum Erfassen von Informationen für eine Fensterklasse.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
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
|[m_atom](#m_atom)|Die registrierten Fensterklasse identifiziert eindeutig.|  
|[m_bSystemCursor](#m_bsystemcursor)|Gibt an, ob der Cursor-Ressource auf einen Systemcursor oder ein Cursor in einem Modul Ressource verweist.|  
|[m_lpszCursorID](#m_lpszcursorid)|Gibt den Namen der Cursorressource.|  
|[m_lpszOrigName](#m_lpszorigname)|Enthält den Namen einer vorhandenen Fensterklasse.|  
|[m_szAutoName](#m_szautoname)|Enthält den Namen einer ATL generierte der Window-Klasse.|  
|[m_wc](#m_wc)|In der fensterklasseninformationen verwaltet einen **WNDCLASSEX** Struktur.|  
|[pWndProc](#pwndproc)|Verweist auf die Fensterprozedur für eine vorhandene Fensterklasse.|  
  
## <a name="remarks"></a>Hinweise  
 `CWndClassInfo`die Informationen für eine Fensterklasse verwaltet. In der Regel `CWndClassInfo` durch eine der drei Makros `DECLARE_WND_CLASS`, `DECLARE_WND_CLASS_EX`, oder `DECLARE_WND_SUPERCLASS`, wie in der folgenden Tabelle beschrieben:  
  
|Makro|Beschreibung|  
|-----------|-----------------|  
|[DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971)|`CWndClassInfo`Informationen für eine neue Windows-Klasse registriert.|  
|[DECLARE_WND_CLASS_EX](http://msdn.microsoft.com/library/0672c144-f2aa-4f6a-ae16-566e3a1f5411)|`CWndClassInfo`Informationen für eine neue Windows-Klasse, einschließlich der Parameter für die Klasse registriert.|  
|[DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd)|`CWndClassInfo`registriert die Informationen für eine Windows-Klasse, die auf einer vorhandenen Klasse basiert, jedoch eine andere Fensterprozedur verwendet. Diese Technik wird das Erstellen von übergeordneten Klassen bezeichnet.|  
  
 In der Standardeinstellung [CWindowImpl](../../atl/reference/cwindowimpl-class.md) enthält die `DECLARE_WND_CLASS` Makro zum Erstellen eines Fensters basierend auf einer neuen Fensterklasse. DECLARE_WND_CLASS werden die Standardstile und die Hintergrundfarbe für das Steuerelement bereitstellt. Wenn geben Sie den Stil und Hintergrundfarbe selbst werden sollen, leiten Sie eine Klasse von `CWindowImpl` und enthalten die `DECLARE_WND_CLASS_EX` Makro in die Klassendefinition.  
  
 Wenn Sie ein Fenster basierend auf eine vorhandene Fensterklasse erstellen möchten, leiten Sie eine Klasse von `CWindowImpl` und enthalten die `DECLARE_WND_SUPERCLASS` Makro in die Klassendefinition. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_Windowing&#43;](../../atl/codesnippet/cpp/cwndclassinfo-class_1.h)]  
  
 Weitere Informationen über Klassen finden Sie unter [Fensterklassen](http://msdn.microsoft.com/library/windows/desktop/ms632596) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zum Verwenden von Fenstern in ATL finden Sie im Artikel [ATL-Fensterklassen](../../atl/atl-window-classes.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  
  
##  <a name="a-namematoma--cwndclassinfomatom"></a><a name="m_atom"></a>CWndClassInfo::m_atom  
 Enthält den eindeutigen Bezeichner für die registrierten Fensterklasse.  
  
```
ATOM m_atom;
```  
  
##  <a name="a-namembsystemcursora--cwndclassinfombsystemcursor"></a><a name="m_bsystemcursor"></a>CWndClassInfo::m_bSystemCursor  
 Wenn **TRUE**, die Cursor Systemressource wird geladen, wenn die Fensterklasse registriert ist.  
  
```
BOOL m_bSystemCursor;
```  
  
### <a name="remarks"></a>Hinweise  
 Andernfalls wird der Cursor-Ressource in Ihrem Modul enthalten geladen werden.  
  
 `CWndClassInfo`verwendet `m_bSystemCursor` nur, wenn die [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971) (die Standardeinstellung für [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) oder die [DECLARE_WND_CLASS_EX](http://msdn.microsoft.com/library/0672c144-f2aa-4f6a-ae16-566e3a1f5411) Makro angegeben ist. In diesem Fall `m_bSystemCursor` wird initialisiert **TRUE**. Weitere Informationen finden Sie unter der [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) (Übersicht).  
  
##  <a name="a-namemlpszcursorida--cwndclassinfomlpszcursorid"></a><a name="m_lpszcursorid"></a>CWndClassInfo::m_lpszCursorID  
 Gibt den Namen der Cursorressource oder den Ressourcenbezeichner in das niederwertige Wort und&0; (null), das höherwertige Wort.  
  
```
LPCTSTR m_lpszCursorID;
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Fensterklasse registriert ist, das Handle für den Cursor identifizierten `m_lpszCursorID` abgerufen und von gespeicherten [M_wc](#m_wc).  
  
 `CWndClassInfo`verwendet `m_lpszCursorID` nur, wenn die [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971) (die Standardeinstellung für [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) oder die [DECLARE_WND_CLASS_EX](http://msdn.microsoft.com/library/0672c144-f2aa-4f6a-ae16-566e3a1f5411) Makro angegeben ist. In diesem Fall `m_lpszCursorID` wird initialisiert **IDC_ARROW**. Weitere Informationen finden Sie unter der [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) (Übersicht).  
  
##  <a name="a-namemlpszorignamea--cwndclassinfomlpszorigname"></a><a name="m_lpszorigname"></a>CWndClassInfo::m_lpszOrigName  
 Enthält den Namen einer vorhandenen Fensterklasse.  
  
```
LPCTSTR m_lpszOrigName;
```  
  
### <a name="remarks"></a>Hinweise  
 `CWndClassInfo`verwendet `m_lpszOrigName` nur wenn enthalten die [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd) Makro in die Klassendefinition. In diesem Fall `CWndClassInfo` Register eine Fensterklasse auf der Klasse mit dem Namen basierend `m_lpszOrigName`. Weitere Informationen finden Sie unter der [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) (Übersicht).  
  
##  <a name="a-namemszautonamea--cwndclassinfomszautoname"></a><a name="m_szautoname"></a>CWndClassInfo::m_szAutoName  
 Enthält den Namen der Fensterklasse.  
  
```
TCHAR m_szAutoName[13];
```  
  
### <a name="remarks"></a>Hinweise  
 `CWndClassInfo`verwendet `m_szAutoName` nur, wenn **NULL** übergeben wird, für die `WndClassName` Parameter [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971), [DECLARE_WND_CLASS_EX](http://msdn.microsoft.com/library/0672c144-f2aa-4f6a-ae16-566e3a1f5411) oder [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd). ATL wird einen Namen erstellen, wenn die Fensterklasse registriert wird.  
  
##  <a name="a-namemwca--cwndclassinfomwc"></a><a name="m_wc"></a>CWndClassInfo::m_wc  
 Verwaltet die fensterklasseninformationen in einem [WNDCLASSEX](http://msdn.microsoft.com/library/windows/desktop/ms633577) Struktur.  
  
```
WNDCLASSEX m_wc;
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie angegeben haben die [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971) (die Standardeinstellung für [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) oder die [DECLARE_WND_CLASS_EX](http://msdn.microsoft.com/library/0672c144-f2aa-4f6a-ae16-566e3a1f5411) -Makro `m_wc` enthält Informationen zu einer neuen Fensterklasse.  
  
 Wenn Sie angegeben haben, die [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd) -Makro `m_wc` enthält Informationen zu einer übergeordneten Klasse – eine Fensterklasse, die auf einer vorhandenen Klasse basiert, jedoch eine andere Fensterprozedur verwendet. [M_lpszOrigName](#m_lpszorigname) und [pWndProc](#pwndproc) speichern Sie die vorhandene Fensterklasse Namen und die Fensterprozedur.  
  
##  <a name="a-namepwndproca--cwndclassinfopwndproc"></a><a name="pwndproc"></a>CWndClassInfo::pWndProc  
 Verweist auf die Fensterprozedur für eine vorhandene Fensterklasse.  
  
```
WNDPROC pWndProc;
```  
  
### <a name="remarks"></a>Hinweise  
 `CWndClassInfo`verwendet `pWndProc` nur wenn enthalten die [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd) Makro in die Klassendefinition. In diesem Fall `CWndClassInfo` registriert eine Fensterklasse, die auf einer vorhandenen Klasse basiert, jedoch eine andere Fensterprozedur verwendet. Die vorhandene Fensterklasse Fensterprozedur wird gespeichert, `pWndProc`. Weitere Informationen finden Sie unter der [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) (Übersicht).  
  
##  <a name="a-nameregistera--cwndclassinforegister"></a><a name="register"></a>CWndClassInfo::Register  
 Aufgerufen von [CWindowImpl:: Create](../../atl/reference/cwindowimpl-class.md#create) Window-Klasse zu registrieren, wenn sie noch nicht registriert wurde.  
  
```
ATOM Register(WNDPROC* pProc);
```  
  
### <a name="parameters"></a>Parameter  
 `pProc`  
 [out] Gibt die ursprüngliche Fensterprozedur der eine vorhandene Fensterklasse.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, ein Atom, identifiziert eindeutig die Fensterklasse registriert wird. Andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Bei Angabe der [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971) (die Standardeinstellung für [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) oder die [DECLARE_WND_CLASS_EX](http://msdn.microsoft.com/library/0672c144-f2aa-4f6a-ae16-566e3a1f5411) -Makro, `Register` eine neue Fensterklasse registriert. In diesem Fall die `pProc` Parameter wird nicht verwendet.  
  
 Wenn Sie angegeben haben, die [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd) -Makro, `Register` registriert eine übergeordnete Klasse – eine Fensterklasse, die auf einer vorhandenen Klasse basiert, jedoch eine andere Fensterprozedur verwendet. In die vorhandene Fensterklasse Fensterprozedur zurückgegeben `pProc`.  
  
## <a name="see-also"></a>Siehe auch  
 [CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
