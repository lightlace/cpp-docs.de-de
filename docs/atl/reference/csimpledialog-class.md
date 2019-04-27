---
title: CSimpleDialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- CSimpleDialog
- ATLWIN/ATL::CSimpleDialog
- ATLWIN/ATL::CSimpleDialog::DoModal
helpviewer_keywords:
- CSimpleDialog class
- CSimpleDialog class, modal dialog boxes in ATL
- dialog boxes, modal
- modal dialog boxes, ATL
ms.assetid: 2ae65cc9-4f32-4168-aecd-200b4a480fdf
ms.openlocfilehash: b0790d9c29b50b1ac454815cd2189e0efb31b9ef
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62278051"
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

*t_bCenter*<br/>
True, wenn das Dialogfeldobjekt im übergeordneten Fenster zentriert werden soll. andernfalls "false".

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSimpleDialog::DoModal](#domodal)|Erstellt ein modales Dialogfeld an.|

## <a name="remarks"></a>Hinweise

Implementiert ein modales Dialogfeld mit grundlegender Funktionalität. `CSimpleDialog` bietet Unterstützung für Windows-Standardsteuerelemente nur. Zum Erstellen und ein modales Dialogfeld anzeigen, erstellen Sie eine Instanz dieser Klasse, die den Namen einer vorhandenen Vorlage für die Ressource angeben, für das Dialogfeld ein. Die Dialogfeldobjekt wird geschlossen, wenn der Benutzer auf jedes Steuerelement mit einem vordefinierten Wert (z. B. IDOK oder IDCANCEL) klickt.

`CSimpleDialog` können Sie nur die modale Dialogfelder zu erstellen. `CSimpleDialog` enthält die Dialogfeldprozedur, die die Standard-meldungszuordnung verwendet werden, um Nachrichten an die entsprechenden Handler zu leiten.

Finden Sie unter [Implementieren eines Dialogfelds](../../atl/implementing-a-dialog-box.md) für Weitere Informationen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CDialogImplBase`

`CSimpleDialog`

## <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="domodal"></a>  CSimpleDialog::DoModal

Ruft ein modales Dialogfeld, und gibt anschließend das Dialogfeld--Ergebnis zurück.

```
INT_PTR DoModal(HWND hWndParent = ::GetActiveWindow());
```

### <a name="parameters"></a>Parameter

*hWndParent*<br/>
Ein Handle für das übergeordnete Element des Dialogfelds. Wenn kein Wert angegeben wird, wird das übergeordnete Element, das momentan aktive Fenster festgelegt.

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, ist der Rückgabewert die Ressourcen-ID des Steuerelements, das das Dialogfeld geschlossen.

Wenn die Funktion fehlschlägt, wird der Wert-1 zurückgegeben. Um erweiterte Fehlerinformationen abzurufen, rufen Sie `GetLastError` auf.

### <a name="remarks"></a>Hinweise

Diese Methode verarbeitet alle Interaktionen mit dem Benutzer, während das Dialogfeld aktiv ist. Dies ist, was die modales Dialogfeld. der Benutzer kann nicht, also mit anderen Windows interagieren, bis das Dialogfeld geschlossen wird.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
