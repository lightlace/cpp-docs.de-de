---
title: Klasse CMFCDisableMenuAnimation | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation::Restore
dev_langs:
- C++
helpviewer_keywords:
- CMFCDisableMenuAnimation class
ms.assetid: c6eb07da-c382-43d6-8028-007f2320e50e
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ea0be944ca70d6f8317fd4bc60fdd50ecc714438
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdisablemenuanimation-class"></a>CMFCDisableMenuAnimation-Klasse
Deaktiviert die Popup-Menüanimation.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCDisableMenuAnimation  
```  
  
## <a name="members"></a>Mitglieder  
  
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
|[CMFCDisableMenuAnimation::Restore](#restore)|Stellt die vorherige Animation, die das Framework verwendet, um ein Popupmenü anzuzeigen.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|Name|Beschreibung|  
|`CMFCDisableMenuAnimation::m_animType`|Speichert den vorherigen Popupmenü Animation-Typ.|  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Hilfsklasse vorübergehend deaktivieren, klicken Sie im Popupmenü Animation (z. B., wenn Sie die Maus oder Tastatur Befehle verarbeiten).  
  
 Ein `CMFCDisableMenuAnimation` Objekt deaktiviert die Popup-Menüanimation während seiner Lebensdauer. Der Konstruktor speichert den aktuellen Popupmenü Animation-Typ in der `m_animType` -Feld und setzt die aktuelle Animation Geben Sie auf `CMFCPopupMenu::NO_ANIMATION`. Der Destruktor wird der vorherige Animationstyp wiederhergestellt.  
  
 Sie erstellen ein `CMFCDisableMenuAnimation` Objekt im Stapel Popupmenü in eine einzelne Funktion deaktivieren. Wenn Sie Popup-Menüanimation zwischen Funktionen deaktivieren möchten, erstellen Sie ein `CMFCDisableMenuAnimation` -Objekt, auf dem Heap, und löschen Sie ihn, wenn Sie im Popupmenü Animation wiederherstellen möchten.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie mit dem Stapel um Menüanimation vorübergehend zu deaktivieren.  
  
 [!code-cpp[NVC_MFC_Misc&#1;](../../mfc/reference/codesnippet/cpp/cmfcdisablemenuanimation-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CMFCDisableMenuAnimation](../../mfc/reference/cmfcdisablemenuanimation-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxpopupmenu.h  
  
##  <a name="restore"></a>CMFCDisableMenuAnimation::Restore  
 Stellt die vorherige Animation, die das Framework verwendet, um ein Popupmenü anzuzeigen.  
  
```  
void Restore ();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem die `CMFCDisableMenuAnimation` Destruktor die vorherige Animation wiederherstellen, die das Framework verwendet wird, um ein Popupmenü anzuzeigen.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCPopupMenu-Klasse](../../mfc/reference/cmfcpopupmenu-class.md)

