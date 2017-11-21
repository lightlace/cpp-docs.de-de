---
title: Allgemeine Ablauffolge bei der Fenstererstellung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- sequence [MFC], window creation
- frame windows [MFC], creating
- windows [MFC], creating
- sequence [MFC]
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4bd939d6deda4f50d03ba0951720aa4d445fcae7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="general-window-creation-sequence"></a>Allgemeine Ablauffolge bei der Fenstererstellung
Wenn Sie ein Fenster eigene, z. B. ein untergeordnetes Fenster erstellen, verwendet das Framework desselben Prozesses als beschrieben [Dokument-/Ansichtarchitektur Erstellung](../mfc/document-view-creation.md).  
  
 Aller Fensterklassen, die von MFC beschäftigen bereitgestellten [zweistufige Konstruktion](../mfc/one-stage-and-two-stage-construction-of-objects.md). D. h. während eines Aufrufs der C++-Komponente **neue** -Operator, der Konstruktor reserviert und initialisiert ein C++-Objekt jedoch keine entsprechenden Windows-Fenster erstellt. Erfolgt anschließend durch Aufrufen der [erstellen](../mfc/reference/cwnd-class.md#create) Memberfunktion des Window-Objekts.  
  
 Die **erstellen** Memberfunktion wird die Windows-Fenster und speichert dessen `HWND` in der C++-Objekt öffentlichen Datenmember [M_hWnd](../mfc/reference/cwnd-class.md#m_hwnd). **Erstellen Sie** bietet vollständige Flexibilität über die Erstellungsparameter. Vor dem Aufruf **erstellen**, Sie möchten eine Fensterklasse mit der globalen Funktion registrieren [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) um die Stile-Symbol und die Klasse für den Frame festzulegen.  
  
 Für das Rahmenfenster, können Sie die [LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) Memberfunktion anstelle der **erstellen**. `LoadFrame`Stellt das Windows-Fenster, die weniger Parameter verwenden. Er ruft zahlreichen Standardwerten aus Ressourcen, einschließlich der Frame Beschriftung, Symbol Zugriffstastentabelle und im Menü ab.  
  
> [!NOTE]
>  Ihr Symbol Zugriffstastentabelle und Menüressourcen benötigen eine allgemeine Ressourcen-ID, wie z. B. **IDR_MAINFRAME**, für sie von LoadFrame geladen werden.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Fensterobjekte](../mfc/window-objects.md)  
  
-   [Registrieren von Fensterklassen""](../mfc/registering-window-classes.md)  
  
-   [Zerstören von Fensterobjekten](../mfc/destroying-window-objects.md)  
  
-   [Erstellen von Dokument Rahmenfenster](../mfc/creating-document-frame-windows.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Fenstern](../mfc/creating-windows.md)

