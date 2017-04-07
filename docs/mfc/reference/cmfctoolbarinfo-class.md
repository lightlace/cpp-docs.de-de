---
title: Klasse CMFCToolBarInfo | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo::m_uiColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuResID
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarInfo class
ms.assetid: 6dc84482-eaaa-491f-aa5d-dd7a57886b46
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
ms.openlocfilehash: a9e66ffa0b5a751a7e5711ed20927a6adcede45d
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarinfo-class"></a>CMFCToolBarInfo-Klasse
Enthält die Ressourcen-IDs von Symbolleistenbildern in unterschiedlichen Zuständen. `CMFCToolBarInfo`ist eine Hilfsklasse, die als Parameter verwendet, wird die [CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) Methode.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCToolBarInfo  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarInfo::m_uiColdResID](#m_uicoldresid)|Ressourcen-ID der Symbolleistenbitmap für die, die Symbolleistenbilder, die reguläre (cold) enthält.|  
|[CMFCToolBarInfo::m_uiDisabledResID](#m_uidisabledresid)|Ressourcen-ID der Symbolleistenbitmap für die, die deaktivierte Symbolleistenbilder enthält.|  
|[CMFCToolBarInfo::m_uiHotResID](#m_uihotresid)|Ressourcen-ID der Symbolleistenbitmap für die, die Symbolleistenbilder, die ausgewählte (hot) enthält.|  
|[CMFCToolBarInfo::m_uiLargeColdResID](#m_uilargecoldresid)|Ressourcen-ID der Symbolleistenbitmap für die, die große, reguläre Symbolleistenbilder enthält.|  
|[CMFCToolBarInfo::m_uiLargeDisabledResID](#m_uilargedisabledresid)|Ressourcen-ID der Symbolleistenbitmap für die, die große enthält deaktiviert Symbolleistenbilder.|  
|[CMFCToolBarInfo::m_uiLargeHotResID](#m_uilargehotresid)|Ressourcen-ID der Symbolleistenbitmap für die, die große, ausgewählte Symbolleistenbilder enthält.|  
|[CMFCToolBarInfo::m_uiMenuDisabledResID](#m_uimenudisabledresid)|Ressourcen-ID der Symbolleistenbitmap für die, die deaktivierten Menübilder enthält.|  
|[CMFCToolBarInfo::m_uiMenuResID](#m_uimenuresid)|Ressourcen-ID der Symbolleistenbitmap für die, die Sie im Menübilder enthält.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Bitmap für die vollständige Symbolleiste besteht aus kleinen Symbolleistenbilder (Felder), die eine feste Größe. Jeder Ressourcen-ID, die in gespeichert ist ein `CMFCToolBarInfo` Objekt ist eine Bitmap, die einen vollständigen Satz von symbolleistenbildern in einem Zustand (z. B., ausgewählte deaktiviert, Groß oder Menübilder) enthält.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CMFCToolBarInfo](../../mfc/reference/cmfctoolbarinfo-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtoolbar.h  
  
##  <a name="m_uicoldresid"></a>CMFCToolBarInfo::m_uiColdResID  
 Gibt eine Ressourcen-ID für die normale Schaltflächenbilder einer Symbolleiste an.  
  
```  
UINT m_uiColdResID;  
```  
  
##  <a name="m_uidisabledresid"></a>CMFCToolBarInfo::m_uiDisabledResID  
 Gibt eine Ressourcen-ID für die Schaltfläche nicht verfügbar-Images von einer Symbolleiste an.  
  
```  
UINT m_uiDisabledResID;  
```  
  
##  <a name="m_uihotresid"></a>CMFCToolBarInfo::m_uiHotResID  
 Gibt eine Ressourcen-ID für die hervorgehobene Schaltflächenbilder einer Symbolleiste an.  
  
```  
UINT m_uiHotResID  
```  
  
##  <a name="m_uilargecoldresid"></a>CMFCToolBarInfo::m_uiLargeColdResID  
 Gibt eine Ressourcen-ID für die große normale Schaltflächenbilder einer Symbolleiste an.  
  
```  
UINT m_uiLargeColdResID  
```  
  
##  <a name="m_uilargedisabledresid"></a>CMFCToolBarInfo::m_uiLargeDisabledResID  
 Gibt eine Ressourcen-ID für die große deaktivierte Schaltflächenbilder einer Symbolleiste an.  
  
```  
UINT m_uiLargeDisabledResID;  
```  
  
##  <a name="m_uilargehotresid"></a>CMFCToolBarInfo::m_uiLargeHotResID  
 Gibt eine Ressourcen-ID für alle großen hervorgehobenen Bilder einer Symbolleiste an.  
  
```  
UINT m_uiLargeHotResID;  
```  
  
##  <a name="m_uimenudisabledresid"></a>CMFCToolBarInfo::m_uiMenuDisabledResID  
 Gibt eine Ressourcen-ID für die Bilder Befehl nicht verfügbar, einer Symbolleiste an.  
  
```  
UINT m_uiMenuDisabledResID;  
```  
  
##  <a name="m_uimenuresid"></a>CMFCToolBarInfo::m_uiMenuResID  
 Gibt eine Ressourcen-ID für alle regulären menüelementbilder einer Symbolleiste an.  
  
```  
UINT m_uiMenuResID;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)

