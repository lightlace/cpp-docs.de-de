---
title: "CWndClassInfo Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWndClassInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWndClassInfo class"
ms.assetid: c36fe7e1-75f1-4cf5-a06f-9f59c43fe6fb
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CWndClassInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Registrieren von Informationen für eine Fensterklasse bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CWndClassInfo  
  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|||  
|-|-|  
|[Register](../Topic/CWndClassInfo::Register.md)|Registriert die Fensterklasse.|  
  
### Datenmember  
  
|||  
|-|-|  
|[m\_atom](../Topic/CWndClassInfo::m_atom.md)|Identifiziert eindeutig die registrierte Fensterklasse.|  
|[m\_bSystemCursor](../Topic/CWndClassInfo::m_bSystemCursor.md)|Gibt an, ob die Cursorressource einen System\-Cursor oder einem Cursor verweist, der in einer Modulressource enthalten ist.|  
|[m\_lpszCursorID](../Topic/CWndClassInfo::m_lpszCursorID.md)|Gibt den Namen der Cursorressource an.|  
|[m\_lpszOrigName](../Topic/CWndClassInfo::m_lpszOrigName.md)|Enthält den Namen einer vorhandenen Fensterklasse.|  
|[m\_szAutoName](../Topic/CWndClassInfo::m_szAutoName.md)|Hält einen ATL\-generierten Namen der Fensterklasse an.|  
|[m\_wc](../Topic/CWndClassInfo::m_wc.md)|Behält Fensterklasseninformationen in einer Struktur **WNDCLASSEX** bei.|  
|[pWndProc](../Topic/CWndClassInfo::pWndProc.md)|Punkte der Fensterprozedur einer vorhandenen Fensterklasse.|  
  
## Hinweise  
 `CWndClassInfo` verwaltet die Informationen einer Fensterklasse.  Sie verwenden in der Regel `CWndClassInfo` durch eines der drei Makros, von `DECLARE_WND_CLASS`, von `DECLARE_WND_CLASS_EX` oder von `DECLARE_WND_SUPERCLASS`, wie in der folgenden Tabelle beschrieben:  
  
|Makro|Description|  
|-----------|-----------------|  
|[DECLARE\_WND\_CLASS](../Topic/DECLARE_WND_CLASS.md)|`CWndClassInfo` Registerinformationen für eine neue Windows\-Klasse.|  
|[DECLARE\_WND\_CLASS\_EX](../Topic/DECLARE_WND_CLASS_EX.md)|`CWndClassInfo` Registerinformationen für eine neue Windows\-Klasse, einschließlich der CLASS\-Parameteren.|  
|[DECLARE\_WND\_SUPERCLASS](../Topic/DECLARE_WND_SUPERCLASS.md)|`CWndClassInfo` Registerinformationen für eine Fensterklasse, die basierend auf einer vorhandenen Klasse, ist jedoch eine andere Fensterprozedur verwendet.  Diese Technik wird Erstellen einer übergeordneten Klasse für aufgerufen.|  
  
 Standardmäßig enthält [CWindowImpl](../../atl/reference/cwindowimpl-class.md) das `DECLARE_WND_CLASS`\-Makro ein, um ein Fenster auf einer neuen Fensterklasse zu erstellen.  DECLARE\_WND\_CLASS stellt Standardstile und Hintergrundfarbe für das Steuerelement.  Wenn Sie das Format und die Hintergrundfarbe angeben möchten sich, leiten Sie die Klasse von `CWindowImpl` und schließen Sie das `DECLARE_WND_CLASS_EX`\-Makro in der Klassendefinition ein.  
  
 Wenn Sie ein Fenster basierend auf einer vorhandenen Fensterklasse erstellen möchten, leiten Sie die Klasse von `CWindowImpl` und schließen Sie das `DECLARE_WND_SUPERCLASS`\-Makro in der Klassendefinition ein.  Beispiel:  
  
 [!CODE [NVC_ATL_Windowing#43](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#43)]  
  
 Weitere Informationen zu Fensterklassen, finden Sie unter [Fensterklassen](http://msdn.microsoft.com/library/windows/desktop/ms632596) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zur Verwendung von Fenstern in ATL, finden Sie im Artikel [ATL\-Fensterklassen](../../atl/atl-window-classes.md).  
  
## Anforderungen  
 **Header:**  atlwin.h  
  
## Siehe auch  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)