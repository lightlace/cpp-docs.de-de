---
title: CSimpleDialog Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CSimpleDialog
- CSimpleDialgo
- CSimpleDialog
- ATL.CSimpleDialog
dev_langs:
- C++
helpviewer_keywords:
- CSimpleDialog class
- CSimpleDialog class, modal dialog boxes in ATL
- dialog boxes, modal
- modal dialog boxes, ATL
ms.assetid: 2ae65cc9-4f32-4168-aecd-200b4a480fdf
caps.latest.revision: 19
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: a4c17a1da8d1be00ebff171af09bc6c8eb81ed44
ms.lasthandoff: 02/24/2017

---
# <a name="csimpledialog-class"></a>CSimpleDialog-Klasse
Diese Klasse implementiert die grundlegende modales Dialogfeld.  
  
## <a name="syntax"></a>Syntax  
  
```
template <WORD t_wDlgTemplateID, BOOL t_bCenter = TRUE>  
class CSimpleDialog : public CDialogImplBase
```  
  
#### <a name="parameters"></a>Parameter  
 *t_wDlgTemplateID*  
  
 Die Ressourcen-ID der Dialogfeldvorlagen-Ressource.  
  
 *t_bCenter*  
 **True,** ist das Dialogfeldobjekt im übergeordneten Fenster zentriertes andernfalls **FALSE**.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleDialog::DoModal](#domodal)|Erstellt ein modales Dialogfeld an.|  
  
## <a name="remarks"></a>Hinweise  
 Implementiert ein modales Dialogfeld mit der grundlegenden Funktionalität. `CSimpleDialog`bietet Unterstützung für allgemeine Windows-Steuerelemente nur. Zum Erstellen und ein modales Dialogfeld anzeigen, erstellen Sie eine Instanz dieser Klasse, die den Namen einer vorhandenen Vorlage für die Ressource für das Dialogfeld bereitstellen. Die Dialogfeldobjekt wird geschlossen, wenn der Benutzer auf jedem Steuerelement mit einem vordefinierten Wert (z. B. IDOK oder IDCANCEL) klickt.  
  
 `CSimpleDialog`können Sie nur modale Dialogfelder zu erstellen. `CSimpleDialog`Stellt die Prozedur für Standarddialogfelder, die die Standardkurve für die Nachricht verwendet wird, um Nachrichten an die entsprechenden Handler zu leiten.  
  
 Finden Sie unter [Implementieren eines Dialogfelds](../../atl/implementing-a-dialog-box.md) Weitere Informationen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CDialogImplBase`  
  
 `CSimpleDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  
  
##  <a name="a-namedomodala--csimpledialogdomodal"></a><a name="domodal"></a>CSimpleDialog::DoModal  
 Ruft ein modales Dialogfeld aus, und gibt das Ergebnis im Dialogfeld nach Abschluss.  
  
```
INT_PTR DoModal(HWND hWndParent = ::GetActiveWindow());
```  
  
### <a name="parameters"></a>Parameter  
 `hWndParent`  
 Ein Handle für das übergeordnete Element des Dialogfelds. Wenn kein Wert angegeben ist, wird das übergeordnete Element, das momentan aktive Fenster festgelegt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, ist der Rückgabewert die Ressourcen-ID des Steuerelements, das das Dialogfeld geschlossen.  
  
 Wenn die Funktion fehlschlägt, ist der Rückgabewert –&1;. Um erweiterte Fehlerinformationen abzurufen, rufen Sie `GetLastError` auf.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode verarbeitet alle Interaktionen mit dem Benutzer, während das Dialogfeld aktiv ist. Dies ist, was die modales Dialogfeld. der Benutzer kann nicht, also mit anderen Fenstern interagieren, bis das Dialogfeld geschlossen wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

