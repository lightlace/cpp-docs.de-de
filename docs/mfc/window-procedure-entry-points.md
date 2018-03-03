---
title: "Einstiegspunkte für Fensterprozeduren | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- state management, window procedures
- MFC, managing state data
- window procedure entry points
- entry points, window procedures
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5f4e99ce38bd5ae472d688dc779bdd4ccf9fd4c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="window-procedure-entry-points"></a>Einstiegspunkte für Fensterprozeduren
MFC-Fensterprozeduren, ein Modul statischen Links mit einer speziellen Fenster Prozedur Implementierung zu schützen. Die Verknüpfung erfolgt automatisch, wenn das Modul mit MFC verknüpft wird. Diese Fensterprozedur verwendet die `AFX_MANAGE_STATE` Makros zu den gültigen Modulstatus ordnungsgemäß festgelegt, und er ruft dann **fxWndProc**, die wiederum delegiert an die `WindowProc` Memberfunktion der entsprechenden `CWnd`-abgeleitet -Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwalten der Statusdaten von MFC-Modulen](../mfc/managing-the-state-data-of-mfc-modules.md)

