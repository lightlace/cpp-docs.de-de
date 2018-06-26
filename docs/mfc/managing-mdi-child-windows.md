---
title: Verwalten von untergeordneten MDI-Fenster | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- MDICLIENT
dev_langs:
- C++
helpviewer_keywords:
- MDI [MFC], child windows
- child windows [MFC], and MDICLIENT window
- MDICLIENT window [MFC]
- windows [MFC], MDI
- frame windows [MFC], MDI child windows
- child windows [MFC]
- MDI [MFC], frame windows
ms.assetid: 1828d96e-a561-48ae-a661-ba9701de6bee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 58ddef11e56da760bbecaa47f03dfa6c57dfa3ed
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929480"
---
# <a name="managing-mdi-child-windows"></a>Verwalten von untergeordneten MDI-Fenstern
MDI-Hauptrahmenfenster (eine pro Anwendung) enthalten ein spezielles untergeordnetes Fenster MDICLIENT-Fenster aufgerufen. MDICLIENT-Fenster verwaltet, das den Clientbereich des Hauptrahmenfenster und selbst untergeordnete Fenster Fehler: das Dokumentfenster abgeleitet `CMDIChildWnd`. Da die Dokumentfenster Rahmenfenstern selbst (untergeordnete MDI-Fenster) sind, können sie außerdem eigene untergeordnete Elemente verfügen. In all diesen Fällen das übergeordnete Fenster zugehöriges untergeordnetes Fenster verwaltet und einige Befehle aus, um diese weiterleitet.  
  
 In einer MDI-Rahmenfenster verwaltet das Rahmenfenster MDICLIENT-Fenster, die in Verbindung mit Schiebeleisten-Steuerelemente neu positionieren. MDICLIENT-Fenster verwaltet wiederum alle MDI-untergeordneten Rahmenfenster. Die folgende Abbildung zeigt die Beziehung zwischen einem MDI-Rahmenfenster, seinem MDICLIENT-Fenster und seine untergeordneten Dokumentrahmenfenster.  
  
 ![Untergeordnete Fenster in ein MDI-Rahmenfenster](../mfc/media/vc37gb1.gif "vc37gb1")  
MDI-Rahmenfenster und untergeordnete Fenster  
  
 Ein MDI-Rahmenfenster funktioniert auch in Verbindung mit der aktuellen untergeordnetes MDI-Fenster, sofern vorhanden. MDI-Rahmenfenster delegiert Command-Meldungen auf untergeordneten MDI-Fensters, bevor sie versucht, die sie selbst behandeln.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Erstellen von Dokument Rahmenfenster](../mfc/creating-document-frame-windows.md)  
  
-   [Rahmenfensterstile](../mfc/frame-window-styles-cpp.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)

