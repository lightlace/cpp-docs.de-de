---
title: NCCALCSIZE_PARAMS-Struktur
ms.date: 11/04/2016
f1_keywords:
- NCCALCSIZE_PARAMS
helpviewer_keywords:
- NCCALCSIZE_PARAMS structure [MFC]
ms.assetid: 3424cd9f-806a-4089-82fb-414187589edf
ms.openlocfilehash: 3dbe1fcdb941a94876dd95a0eed86d6f4a3e15c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443770"
---
# <a name="nccalcsizeparams-structure"></a>NCCALCSIZE_PARAMS-Struktur

Die `NCCALCSIZE_PARAMS` Struktur enthält Informationen, die eine Anwendung bei der Nachrichtenverarbeitung WM_NCCALCSIZE verwenden kann, um die Größe, Position und gültigen Inhalt des Clientbereichs eines Fensters zu berechnen.

## <a name="syntax"></a>Syntax

```
typedef struct tagNCCALCSIZE_PARAMS {
    RECT rgrc[3];
    PWINDOWPOS lppos;
} NCCALCSIZE_PARAMS;
```

#### <a name="parameters"></a>Parameter

*rgrc*<br/>
Gibt ein Array von Rechtecken. Die erste enthält die neuen Koordinaten eines Fensters, die verschoben oder geändert wurde. Die zweite enthält die Koordinaten des Fensters auf, bevor es verschoben oder ihre Größe geändert wurde. Die dritte enthält die Koordinaten des Clientbereichs eines Fensters aus, bevor es verschoben oder ihre Größe geändert wurde. Wenn das Fenster ein untergeordnetes Fenster ist, sind die Koordinaten relativ zum Clientbereich des übergeordneten Fensters. Wenn das Fenster der obersten Ebene ist, sind die Koordinaten relativ zum Bildschirm an.

*lppos*<br/>
Verweist auf eine [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) -Struktur, die in die Operation, verursacht das Fenster verschoben oder angepasst werden, angegebenen Größe und Position-Werte enthält.

## <a name="requirements"></a>Anforderungen

**Header:** winuser.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)

