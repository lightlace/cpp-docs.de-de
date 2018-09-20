---
title: Einstiegspunkte für Fensterprozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- state management, window procedures
- MFC, managing state data
- window procedure entry points
- entry points, window procedures
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c3226df51d2a83484de78d0d76c9af67e150e8eb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403187"
---
# <a name="window-procedure-entry-points"></a>Einstiegspunkte für Fensterprozeduren

Auf Fensterprozeduren MFC-Modul statischen Links mit einem speziellen Fenster-Implementierung der Prozedur zu schützen. Die Verknüpfung erfolgt automatisch, wenn das Modul mit MFC verknüpft wird. Diese Prozedur verwendet das AFX_MANAGE_STATE-Makro, um den gültigen Modulstatus ordnungsgemäß festgelegt, und es ruft dann `AfxWndProc`, die wiederum delegiert an die `WindowProc` -Memberfunktion des entsprechenden `CWnd`-abgeleitetes Objekt.

## <a name="see-also"></a>Siehe auch

[Verwalten der Statusdaten von MFC-Modulen](../mfc/managing-the-state-data-of-mfc-modules.md)

