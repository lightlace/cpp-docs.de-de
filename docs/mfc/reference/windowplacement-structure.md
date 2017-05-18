---
title: WINDOWPLACEMENT-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WINDOWPLACEMENT
dev_langs:
- C++
helpviewer_keywords:
- WINDOWPLACEMENT structure
ms.assetid: ea7d61f6-eb57-478e-9b08-7c1d07091aa8
caps.latest.revision: 11
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
ms.openlocfilehash: 62cf7003f43d50d5998dd527ae5ad7b10ab95686
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="windowplacement-structure"></a>WINDOWPLACEMENT-Struktur
Die `WINDOWPLACEMENT` Struktur enthält Informationen über die Platzierung eines Fensters auf dem Bildschirm**.**  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct tagWINDOWPLACEMENT {     /* wndpl */  
    UINT length;  
    UINT flags;  
    UINT showCmd;  
    POINT ptMinPosition;  
    POINT ptMaxPosition;  
    RECT rcNormalPosition;  
} WINDOWPLACEMENT;  
```  
  
#### <a name="parameters"></a>Parameter  
 *length*  
 Gibt die Länge in Bytes, der Struktur**.**  
  
 `flags`  
 Gibt Flags an, die die Position eines minimierten Fensters und der Methode, die mit der Fenster wiederhergestellt wird. Dieser Member kann eine oder beide der folgenden Werte sein:  
  
- **WPF_SETMINPOSITION** gibt an, dass die x und y-Position des minimierten Fensters angegeben werden können**.** Dieses Flag muss angegeben werden, wenn die Koordinaten, in festgelegt werden der **PtMinPosition** Element.  
  
- **WPF_RESTORETOMAXIMIZED** gibt an, dass das wiederhergestellte Fenster maximiert werden wird, unabhängig davon, ob es maximiert wurde, bevor er minimiert wurde. Diese Einstellung gilt nur das nächste Mal das Fenster wiederhergestellt wird. Er ändert nicht das Standardverhalten für die Wiederherstellung. Dieses Flag ist nur gültig, wenn die **SW_SHOWMINIMIZED** angegebene Wert ist die **ShowCmd** Member.  
  
 *showCmd*  
 Gibt den aktuellen Anzeigestatus des Fensters. Dieser Member kann einen der folgenden Werte sein:  
  
- **SW_HIDE** Blendet das Fenster aus und übergibt die Aktivierung zu einem anderen Fenster.  
  
- **SW_MINIMIZE** minimiert das angegebene Fenster und das Fenster das obersten Ebene in der Liste des Systems aktiviert.  
  
- **SW_RESTORE** aktiviert und ein Fenster angezeigt. Wenn das Fenster minimiert oder maximiert wird, wird Windows diese in seiner ursprünglichen Größe und Position (identisch mit **SW_SHOWNORMAL**).  
  
- **SW_SHOW** aktiviert ein Fenster und zeigt es in seiner aktuellen Größe und Position.  
  
- **SW_SHOWMAXIMIZED** aktiviert ein Fenster und zeigt ihn als eines maximierten Fensters.  
  
- **SW_SHOWMINIMIZED** aktiviert ein Fenster und als Symbol angezeigt.  
  
- **SW_SHOWMINNOACTIVE** ein Fenster als Symbol angezeigt. Das derzeit aktive Fenster bleibt aktiv.  
  
- **SW_SHOWNA** zeigt ein Fenster in seinem aktuellen Zustand. Das derzeit aktive Fenster bleibt aktiv.  
  
- **SW_SHOWNOACTIVATE** zeigt ein Fenster in der letzten Größe und Position. Das derzeit aktive Fenster bleibt aktiv.  
  
- **SW_SHOWNORMAL** aktiviert und ein Fenster angezeigt. Wenn das Fenster minimiert oder maximiert wird, wird Windows diese in seiner ursprünglichen Größe und Position (identisch mit **SW_RESTORE**).  
  
 *ptMinPosition*  
 Gibt die Position der oberen linken Fensterecke an, wenn das Fenster minimiert wird.  
  
 `ptMaxPosition`  
 Gibt die Position der oberen linken Fensterecke an, wenn das Fenster maximiert ist.  
  
 *rcNormalPosition*  
 Das Fenster Koordinaten angibt, wenn das Fenster in der normalen Position (wiederhergestellt) ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winuser.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::SetWindowPlacement](../../mfc/reference/cwnd-class.md#setwindowplacement)


