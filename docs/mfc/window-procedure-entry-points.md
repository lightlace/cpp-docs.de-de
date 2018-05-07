---
title: Einstiegspunkte für Fensterprozeduren | Microsoft Docs
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
ms.openlocfilehash: 1095061cce8ff8f189984aca99a06eb741a46e83
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="window-procedure-entry-points"></a>Einstiegspunkte für Fensterprozeduren
MFC-Fensterprozeduren, ein Modul statischen Links mit einer speziellen Fenster Prozedur Implementierung zu schützen. Die Verknüpfung erfolgt automatisch, wenn das Modul mit MFC verknüpft wird. Diese Fensterprozedur verwendet die `AFX_MANAGE_STATE` Makros zu den gültigen Modulstatus ordnungsgemäß festgelegt, und er ruft dann **fxWndProc**, die wiederum delegiert an die `WindowProc` Memberfunktion der entsprechenden `CWnd`-abgeleitet -Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwalten der Statusdaten von MFC-Modulen](../mfc/managing-the-state-data-of-mfc-modules.md)

