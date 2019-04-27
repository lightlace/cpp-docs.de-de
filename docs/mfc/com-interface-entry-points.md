---
title: Einstiegspunkte für COM-Schnittstellen
ms.date: 03/27/2019
helpviewer_keywords:
- entry points, COM interfaces
- state management, OLE/COM interfaces
- MFC COM, COM interface entry points
- OLE, interface entry points
- MFC, managing state data
- COM interfaces, entry points
ms.assetid: 9e7421dc-0731-4748-9e1b-90acbaf26d77
ms.openlocfilehash: eb8fc425d6b9849f6367d9b207e5181652386be3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207851"
---
# <a name="com-interface-entry-points"></a>Einstiegspunkte für COM-Schnittstellen

Verwenden Sie für die Member-Funktionen einer COM-Schnittstelle, die `METHOD_PROLOGUE` Makro, um den richtigen globalen Status verwalten, beim Aufrufen von Methoden einer exportierten Schnittstelle.

In der Regel Memberfunktionen von Schnittstellen implementiert, indem `CCmdTarget`-abgeleitete Objekte bereits verwenden Sie dieses Makro, geben Sie die automatische Initialisierung von der `pThis` Zeiger. Zum Beispiel:

[!code-cpp[NVC_MFCConnectionPoints#5](../mfc/codesnippet/cpp/com-interface-entry-points_1.cpp)]

Weitere Informationen finden Sie unter [technischen Hinweis 38](../mfc/tn038-mfc-ole-iunknown-implementation.md) auf MFC/OLE `IUnknown` Implementierung.

Die `METHOD_PROLOGUE` -Makro ist definiert als:

```cpp
#define METHOD_PROLOGUE(theClass, localClass) \
    theClass* pThis = \
    ((theClass*)((BYTE*)this - offsetof(theClass, m_x##localClass))); \
    AFX_MANAGE_STATE(pThis->m_pModuleState) \
```

Der Teil des Makros für die Verwaltung von den globalen Zustand ist:

`AFX_MANAGE_STATE( pThis->m_pModuleState )`

In diesem Ausdruck *M_pModuleState* wird als eine Membervariable des enthaltenden Objekts. Es wird implementiert, indem die `CCmdTarget` Basisklasse und initialisiert wird, auf den entsprechenden Wert von `COleObjectFactory`, wenn das Objekt instanziiert wird.

## <a name="see-also"></a>Siehe auch

[Verwalten der Statusdaten von MFC-Modulen](../mfc/managing-the-state-data-of-mfc-modules.md)
