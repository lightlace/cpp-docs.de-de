---
title: CSimpleDialog Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleDialog
- ATLWIN/ATL::CSimpleDialog
- ATLWIN/ATL::CSimpleDialog::DoModal
dev_langs:
- C++
helpviewer_keywords:
- CSimpleDialog class
- CSimpleDialog class, modal dialog boxes in ATL
- dialog boxes, modal
- modal dialog boxes, ATL
ms.assetid: 2ae65cc9-4f32-4168-aecd-200b4a480fdf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f3a8f6cb2ead8798b86d65a1fa875a42a68cdd77
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="csimpledialog-class"></a>CSimpleDialog-Klasse
Diese Klasse implementiert grundlegende modales Dialogfeld an.  
  
## <a name="syntax"></a>Syntax  
  
```
template <WORD t_wDlgTemplateID, BOOL t_bCenter = TRUE>  
class CSimpleDialog : public CDialogImplBase
```  
  
#### <a name="parameters"></a>Parameter  
 *t_wDlgTemplateID*  
  
 Die Ressourcen-ID der Dialogfeldvorlagen-Ressource.  
  
 *t_bCenter*  
 **"True"** Wenn das Dialogfeldobjekt werden soll, andernfalls auf das besitzende Fenster zentriertes **"false"**.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleDialog::DoModal](#domodal)|Erstellt ein modales Dialogfeld an.|  
  
## <a name="remarks"></a>Hinweise  
 Ein modales Dialogfeld implementiert mit grundlegenden Funktionen. `CSimpleDialog` bietet Unterstützung für Windows-Standardsteuerelemente nur. Erstellen und ein modales Dialogfeld anzeigen, erstellen Sie eine Instanz dieser Klasse, die den Namen einer vorhandenen Vorlage für die Ressource für das Dialogfeld bereitstellen. Die Dialogfeldobjekt schließt klickt der Benutzer jedes Steuerelement mit vordefinierten Werten (z. B. IDOK oder IDCANCEL).  
  
 `CSimpleDialog` können Sie nur modale Dialogfelder zu erstellen. `CSimpleDialog` Stellt die für Standarddialogfelder, die die Standard-meldungszuordnung zur Weiterleitung von Nachrichten an die entsprechenden Handler verwendet.  
  
 Finden Sie unter [Implementieren eines Dialogfelds](../../atl/implementing-a-dialog-box.md) für Weitere Informationen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CDialogImplBase`  
  
 `CSimpleDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  
  
##  <a name="domodal"></a>  CSimpleDialog::DoModal  
 Ruft ein modales Dialogfeld auf und gibt das Ergebnis im Dialogfeld nach Abschluss zurück.  
  
```
INT_PTR DoModal(HWND hWndParent = ::GetActiveWindow());
```  
  
### <a name="parameters"></a>Parameter  
 `hWndParent`  
 Ein Handle für das übergeordnete Element des Dialogfelds. Wenn kein Wert angegeben ist, wird das übergeordnete Element auf der aktuellen aktiven Fensters festgelegt.  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall wird der Rückgabewert die Ressourcen-ID des Steuerelements, das das Dialogfeld geschlossen.  
  
 Wenn die Funktion fehlschlägt, ist der Rückgabewert-1 zurück. Um erweiterte Fehlerinformationen abzurufen, rufen Sie `GetLastError` auf.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode behandelt alle Interaktionen mit dem Benutzer, während das Dialogfeld aktiv ist. Dies ist, was die modales Dialogfeld. d. h. kann nicht der Benutzer mit anderen Fenstern interagieren, bis das Dialogfeld geschlossen wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
