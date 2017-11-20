---
title: "Einstiegspunkte für COM-Schnittstellen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- entry points, COM interfaces
- state management, OLE/COM interfaces
- MFC COM, COM interface entry points
- OLE, interface entry points
- MFC, managing state data
- COM interfaces, entry points
ms.assetid: 9e7421dc-0731-4748-9e1b-90acbaf26d77
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4d551c3875a2c8aca235437579db2f467f680380
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="com-interface-entry-points"></a>Einstiegspunkte für COM-Schnittstellen
Verwenden Sie die Memberfunktionen einer COM-Schnittstelle, die [METHOD_PROLOGUE](com-interface-entry-points.md#method_prologue) Makro, um den richtigen globalen Status beizubehalten, beim Aufrufen von Methoden einer exportierten Schnittstelle.  
  
 In der Regel Memberfunktionen von Schnittstellen implementiert, indem `CCmdTarget`-abgeleitete Objekte bereits dieses Makro verwenden, für die automatische Initialisierung Bereitstellen der `pThis` Zeiger. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCConnectionPoints#5](../mfc/codesnippet/cpp/com-interface-entry-points_1.cpp)]  
  
 Weitere Informationen finden Sie unter [technischen Hinweis 38](../mfc/tn038-mfc-ole-iunknown-implementation.md) auf MFC/OLE **IUnknown** Implementierung.  
  
 Die `METHOD_PROLOGUE` -Makro wird definiert als:  
  
 `#define METHOD_PROLOGUE(theClass, localClass) \`  
  
 `theClass* pThis = \`  
  
 `((theClass*)((BYTE*)this - offsetof(theClass, m_x##localClass))); \`  
  
 `AFX_MANAGE_STATE(pThis->m_pModuleState) \`  
  
 Der Teil des Makros dürfte Verwalten des globalen Status lautet:  
  
 `AFX_MANAGE_STATE( pThis->m_pModuleState )`  
  
 In diesem Ausdruck *M_pModuleState* wird davon ausgegangen, dass eine Membervariable des enthaltenden Objekts. Durch die Implementierung erfolgt die `CCmdTarget` Basisklasse und wird mit den entsprechenden Wert von initialisiert `COleObjectFactory`, bei der Instanziierung des Objekts.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwalten der Statusdaten von MFC-Modulen](../mfc/managing-the-state-data-of-mfc-modules.md)

