---
title: Verwalten von untergeordneten MDI-Fenster | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MDICLIENT
dev_langs: C++
helpviewer_keywords:
- MDI [MFC], child windows
- child windows [MFC], and MDICLIENT window
- MDICLIENT window [MFC]
- windows [MFC], MDI
- frame windows [MFC], MDI child windows
- child windows [MFC]
- MDI [MFC], frame windows
ms.assetid: 1828d96e-a561-48ae-a661-ba9701de6bee
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5ebcd6e484385ada3cd3d5ccfe450e7e25f539eb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="managing-mdi-child-windows"></a>Verwalten von untergeordneten MDI-Fenstern
MDI-Hauptrahmenfenster (eine pro Anwendung) enthalten ein spezielles untergeordnetes Fenster aufgerufen, die **MDICLIENT** Fenster. Der **MDICLIENT** Fenster verwaltet, das den Clientbereich des Hauptrahmenfenster und selbst untergeordnete Fenster Fehler: das Dokumentfenster abgeleitet `CMDIChildWnd`. Da die Dokumentfenster Rahmenfenstern selbst (untergeordnete MDI-Fenster) sind, können sie außerdem eigene untergeordnete Elemente verfügen. In all diesen Fällen das übergeordnete Fenster zugehöriges untergeordnetes Fenster verwaltet und einige Befehle aus, um diese weiterleitet.  
  
 In einer MDI-Rahmenfenster das Rahmenfenster verwaltet die **MDICLIENT** Fenster zusammen mit Schiebeleisten-Steuerelemente neu positionieren. Die **MDICLIENT** Fenster verwaltet wiederum alle MDI-untergeordneten Rahmenfenster. Die folgende Abbildung zeigt die Beziehung zwischen einem MDI-Rahmenfenster seine **MDICLIENT** Fenster und seine untergeordneten Dokumentrahmenfenster.  
  
 ![Untergeordnete Fenster in ein MDI-Rahmenfenster](../mfc/media/vc37gb1.gif "vc37gb1")  
MDI-Rahmenfenster und untergeordnete Fenster  
  
 Ein MDI-Rahmenfenster funktioniert auch in Verbindung mit der aktuellen untergeordnetes MDI-Fenster, sofern vorhanden. MDI-Rahmenfenster delegiert Command-Meldungen auf untergeordneten MDI-Fensters, bevor sie versucht, die sie selbst behandeln.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Erstellen von Dokument Rahmenfenster](../mfc/creating-document-frame-windows.md)  
  
-   [Rahmenfensterstile](../mfc/frame-window-styles-cpp.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)

