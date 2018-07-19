---
title: Behandeln von reflektierten Meldungen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message handling [MFC], reflected messages
- reflected messages, handling
ms.assetid: 147a4e0c-51cc-4447-a8e1-c28b4cece578
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b317f4c1b55e04f61aa0639bbd6953e5f36187a
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931839"
---
# <a name="handling-reflected-messages"></a>Behandeln von reflektierten Meldungen
Nachricht Reflektion können Sie die Meldungen für ein Steuerelement zu verarbeiten, z. B. **WM_CTLCOLOR**, **WM_COMMAND**, und **WM_NOTIFY**, innerhalb des Steuerelements selbst. Dadurch wird das Steuerelement mehr unabhängige und übertragbare. Der Mechanismus funktioniert mit allgemeinen Windows-Steuerelemente sowie mit ActiveX-Steuerelementen (früher OLE-Steuerelemente).  
  
 Nachricht Reflektion können Sie die Wiederverwendung der `CWnd`-schneller abgeleitete Klassen. Reflektion funktioniert über Message [CWnd:: OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify), mit speziellen **ON_XXX_REFLECT** Nachricht Zuordnungseinträge: z. B. **ON_CTLCOLOR_REFLECT** und **ON_CONTROL_REFLECT**. [Technische Hinweis 62](../mfc/tn062-message-reflection-for-windows-controls.md) Meldungsreflektion ausführlicher erläutert.  
  
## <a name="what-do-you-want-to-do"></a>Was möchten Sie tun  
  
-   [Erfahren Sie mehr über meldungsreflexion](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [Implementieren von Meldungsreflektion für ein allgemeines Steuerelement](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [Implementieren von Meldungsreflektion für ein ActiveX-Steuerelement](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Deklarieren von Meldungshandlerfunktionen](../mfc/declaring-message-handler-functions.md)
