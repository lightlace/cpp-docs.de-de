---
title: COleControlModule Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 196b69a0d86c3809415e030adb567c8642051f40
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="colecontrolmodule-class"></a>COleControlModule-Klasse
Die Basisklasse, von der ein OLE-Steuerelementmodul-Objekt abgeleitet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleControlModule : public CWinApp  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse bietet Memberfunktionen zum Initialisieren des Steuerelement-Moduls. Jedes Modul der OLE-Steuerelement, die Microsoft Foundation Classes verwendet darf nur ein Objekt abgeleitet wurde. `COleControlModule`. Dieses Objekt wird erstellt, wenn andere globale C++-Objekte erstellt werden. Deklarieren Sie die abgeleiteten `COleControlModule` Objekt auf globaler Ebene.  
  
 Weitere Informationen zur Verwendung der `COleControlModule` Klasse, finden Sie unter der [CWinApp](../../mfc/reference/cwinapp-class.md) Klasse und die Artikel [ActiveX-Steuerelemente](../../mfc/mfc-activex-controls.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 `COleControlModule`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxctl.h  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel TESTHELP](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



