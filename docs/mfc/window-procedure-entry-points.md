---
title: Einstiegspunkte für Fensterprozeduren
ms.date: 11/04/2016
helpviewer_keywords:
- state management, window procedures
- MFC, managing state data
- window procedure entry points
- entry points, window procedures
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
ms.openlocfilehash: 6d91e2c432588afc5a84f7189fa87a7fc2531b1a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57288628"
---
# <a name="window-procedure-entry-points"></a>Einstiegspunkte für Fensterprozeduren

Auf Fensterprozeduren MFC-Modul statischen Links mit einem speziellen Fenster-Implementierung der Prozedur zu schützen. Die Verknüpfung erfolgt automatisch, wenn das Modul mit MFC verknüpft wird. Diese Prozedur verwendet das AFX_MANAGE_STATE-Makro, um den gültigen Modulstatus ordnungsgemäß festgelegt, und es ruft dann `AfxWndProc`, die wiederum delegiert an die `WindowProc` -Memberfunktion des entsprechenden `CWnd`-abgeleitetes Objekt.

## <a name="see-also"></a>Siehe auch

[Verwalten der Statusdaten von MFC-Modulen](../mfc/managing-the-state-data-of-mfc-modules.md)
