---
title: COleControlModule-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- OleControlModule
dev_langs:
- C++
helpviewer_keywords:
- OLE control modules [MFC]
- MFC ActiveX controls [MFC], OLE control modules
- COleControlModule class [MFC]
- control modules [MFC]
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8139f9d2249e2ed4293c5aad7c87f4f59142b393
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388981"
---
# <a name="colecontrolmodule-class"></a>COleControlModule-Klasse

Die Basisklasse, von der ein OLE-Steuerelementmodul-Objekt abgeleitet wird.

## <a name="syntax"></a>Syntax

```
class COleControlModule : public CWinApp
```

## <a name="remarks"></a>Hinweise

Diese Klasse bietet Memberfunktionen zum Initialisieren von Ihrem Moduls an. Jedes Modul der OLE-Steuerelement, die Microsoft Foundation Classes verwendet darf nur ein Objekt abgeleitet `COleControlModule`. Dieses Objekt wird erstellt, wenn es sich bei anderen globalen C++-Objekte erstellt werden. Deklarieren Ihrer abgeleiteten `COleControlModule` Objekt auf globaler Ebene.

Weitere Informationen zur Verwendung der `COleControlModule` Klasse, finden Sie unter der [CWinApp](../../mfc/reference/cwinapp-class.md) -Klasse und den Artikel [ActiveX-Steuerelemente](../../mfc/mfc-activex-controls.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWinThread](../../mfc/reference/cwinthread-class.md)

[CWinApp](../../mfc/reference/cwinapp-class.md)

`COleControlModule`

## <a name="requirements"></a>Anforderungen

**Header:** afxctl.h

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel TESTHELP](../../visual-cpp-samples.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)



