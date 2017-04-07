---
title: COleControlModule Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- OleControlModule
dev_langs:
- C++
helpviewer_keywords:
- OLE control modules
- MFC ActiveX controls, OLE control modules
- COleControlModule class
- control modules
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
caps.latest.revision: 23
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
ms.sourcegitcommit: 5c6fbfc8699d7d66c40b0458972d8b6ef0dcc705
ms.openlocfilehash: 2e77c386875d25f47f0cc07eb3b7d315f1678c56
ms.lasthandoff: 02/24/2017

---
# <a name="colecontrolmodule-class"></a>COleControlModule-Klasse
Die Basisklasse, von der ein OLE-Steuerelementmodul-Objekt abgeleitet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleControlModule : public CWinApp  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse bietet Memberfunktionen zum Initialisieren des Steuerelement-Moduls. Jedes OLE-Steuerelement-Modul, die Microsoft Foundation Classes verwendet, kann nur ein abgeleitetes Objekt enthalten `COleControlModule`. Dieses Objekt wird erstellt, wenn andere globale C++-Objekte erstellt werden. Deklarieren der abgeleiteten `COleControlModule` Objekt auf globaler Ebene.  
  
 Weitere Informationen zur Verwendung der `COleControlModule` Klasse, finden Sie unter der [CWinApp](../../mfc/reference/cwinapp-class.md) -Klasse und im Artikel [ActiveX-Steuerelemente](../../mfc/mfc-activex-controls.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 `COleControlModule`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxctl.h  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel TESTHELP](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




