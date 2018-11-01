---
title: WINDOWPLACEMENT-Struktur
ms.date: 11/04/2016
f1_keywords:
- WINDOWPLACEMENT
helpviewer_keywords:
- WINDOWPLACEMENT structure [MFC]
ms.assetid: ea7d61f6-eb57-478e-9b08-7c1d07091aa8
ms.openlocfilehash: fecca306045805661a7799aca8d9ea57ea11f5b8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518676"
---
# <a name="windowplacement-structure"></a>WINDOWPLACEMENT-Struktur

Die `WINDOWPLACEMENT` Struktur enthält Informationen zur Platzierung eines Fensters auf dem Bildschirm.

## <a name="syntax"></a>Syntax

```
typedef struct tagWINDOWPLACEMENT {     /* wndpl */
    UINT length;
    UINT flags;
    UINT showCmd;
    POINT ptMinPosition;
    POINT ptMaxPosition;
    RECT rcNormalPosition;
} WINDOWPLACEMENT;
```

#### <a name="parameters"></a>Parameter

*length*<br/>
Gibt die Länge in Bytes, der die Struktur an.

*flags*<br/>
Gibt Flags an, die steuern, die Position eines minimierten Fensters und der Methode, die mit der Fenster wiederhergestellt wird. Dieser Member kann es sich um eine oder beide der folgenden Flags sein:

- WPF_SETMINPOSITION gibt an, dass die x und y-Position der minimierten Fensters angegeben werden können. Dieses Flag muss angegeben werden, wenn die Koordinaten, in festgelegt werden der `ptMinPosition` Member.

- WPF_RESTORETOMAXIMIZED gibt an, dass das wiederhergestellte Fenster maximiert werden wird, unabhängig davon, ob es maximiert wurde vor dem wurde minimiert. Diese Einstellung gilt nur das nächste Mal das Fenster wiederhergestellt wird. Es ändert sich nicht auf das Standardverhalten für die Wiederherstellung aus. Dieses Flag gilt nur, wenn der SW_SHOWMINIMIZED für angegebene Wert ist die `showCmd` Member.

*showCmd*<br/>
Gibt den aktuellen Anzeigestatus des Fensters an. Dieser Member kann einen der folgenden Werte sein:

- SW_HIDE Blendet das Fenster aus und übergibt die Aktivierung in ein anderes Fenster.

- SW_MINIMIZE minimiert das angegebene Fenster und die Fenster das obersten Ebene in der Liste der aktiviert.

- SW_RESTORE aktiviert und ein Fenster angezeigt. Wenn das Fenster minimiert oder maximiert ist, stellt Windows es seine ursprüngliche Größe und Position (identisch mit entweder "SW_SHOWNORMAL").

- SW_SHOW aktiviert ein Fenster und zeigt es in seiner aktuellen Größe und Position.

- "Sw_showmaximized" aktiviert ein Fenster und zeigt ihn als ein maximiertes Fenster.

- SW_SHOWMINIMIZED aktiviert ein Fenster und wird als Symbol angezeigt.

- SW_SHOWMINNOACTIVE zeigt ein Fenster als Symbol. Die derzeit aktive Fenster bleibt aktiv.

- SW_SHOWNA zeigt ein Fenster im aktuellen Zustand. Die derzeit aktive Fenster bleibt aktiv.

- SW_SHOWNOACTIVATE zeigt ein Fenster, in der letzten Größe und Position. Die derzeit aktive Fenster bleibt aktiv.

- Entweder "SW_SHOWNORMAL" aktiviert und ein Fenster angezeigt. Wenn das Fenster minimiert oder maximiert ist, auf wiederhergestellt werden Windows kann die ursprüngliche Größe und Position (identisch mit den SW_RESTORE).

*ptMinPosition*<br/>
Gibt die Position der linke obere Ecke des Fensters an, wenn das Fenster minimiert ist.

*ptMaxPosition*<br/>
Gibt die Position der linke obere Ecke des Fensters an, wenn das Fenster maximiert ist.

*rcNormalPosition*<br/>
Gibt des Fensters Koordinaten an, wenn das Fenster in die Position des normalen (wiederhergestellt) ist.

## <a name="requirements"></a>Anforderungen

**Header:** winuser.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::SetWindowPlacement](../../mfc/reference/cwnd-class.md#setwindowplacement)

