---
title: CMFCDisableMenuAnimation Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation::Restore
dev_langs:
- C++
helpviewer_keywords:
- CMFCDisableMenuAnimation [MFC], Restore
ms.assetid: c6eb07da-c382-43d6-8028-007f2320e50e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 458a35e708db41ee393da70aedd653aca44cf802
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcdisablemenuanimation-class"></a>CMFCDisableMenuAnimation-Klasse
Deaktiviert die Animation im Popupmenü.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCDisableMenuAnimation  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Beschreibung|  
|`CMFCDisableMenuAnimation::CMFCDisableMenuAnimation`|Erstellt ein `CMFCDisableMenuAnimation`-Objekt.|  
|`CMFCDisableMenuAnimation::~CMFCDisableMenuAnimation`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCDisableMenuAnimation::Restore](#restore)|Stellt wieder her dem vorherigen Animation an, der das Framework verwendet wird, um ein Popupmenü anzuzeigen.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|name|Beschreibung|  
|`CMFCDisableMenuAnimation::m_animType`|Speichert den vorherigen Popupmenü Animation-Typ.|  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Hilfsklasse Popupmenü Animation (z. B. bei der Verarbeitung von Befehlen, Maus oder Tastatur) vorübergehend deaktivieren.  
  
 Ein `CMFCDisableMenuAnimation` Objekt deaktiviert die Popupmenü Animation während seiner Lebensdauer. Der Konstruktor speichert den aktuellen Popupmenü Animation-Typ in der `m_animType` -Feld und setzt die aktuelle Animation geben, um `CMFCPopupMenu::NO_ANIMATION`. Der Destruktor wird den vorherige Animationstyp wiederhergestellt.  
  
 Sie erstellen eine `CMFCDisableMenuAnimation` Objekt auf dem Stapel Popupmenü Animation in der gesamten eine einzelne Funktion deaktivieren. Wenn Sie Popup-Menüanimation zwischen Funktionen deaktivieren möchten, erstellen Sie eine `CMFCDisableMenuAnimation` Objekt auf dem Heap, und dann löschen, wenn Sie im Popupmenü Animation wiederherstellen möchten.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie auf den Stapel zu verwenden, um die Menüanimation vorübergehend deaktivieren.  
  
 [!code-cpp[NVC_MFC_Misc#1](../../mfc/reference/codesnippet/cpp/cmfcdisablemenuanimation-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CMFCDisableMenuAnimation](../../mfc/reference/cmfcdisablemenuanimation-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxpopupmenu.h  
  
##  <a name="restore"></a>CMFCDisableMenuAnimation::Restore  
 Stellt wieder her dem vorherigen Animation an, der das Framework verwendet wird, um ein Popupmenü anzuzeigen.  
  
```  
void Restore ();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem die `CMFCDisableMenuAnimation` Destruktor die vorherige Animation wiederherzustellen, die das Framework verwendet wird, um ein Popupmenü anzuzeigen.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCPopupMenu-Klasse](../../mfc/reference/cmfcpopupmenu-class.md)
