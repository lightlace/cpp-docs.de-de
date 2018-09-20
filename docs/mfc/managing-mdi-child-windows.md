---
title: Verwalten die untergeordnete Windows MDI | Microsoft-Dokumentation
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
ms.openlocfilehash: 45989b7c07d27db1d7b2cda68751bd6165ee5382
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428277"
---
# <a name="managing-mdi-child-windows"></a>Verwalten von untergeordneten MDI-Fenstern

MDI-Hauptrahmenfenster (eine pro Anwendung) enthalten spezielle untergeordnete Fenster MDICLIENT-Fenster. MDICLIENT-Fenster verwaltet, das den Clientbereich des Hauptrahmenfenster und selbst verfügt über die untergeordneten Fenster: die Dokumentfenster, das von abgeleiteten `CMDIChildWnd`. Da die Dokumentfenster-Frame-Fensters selbst (untergeordnete MDI-Fenster) sind, Sie können auch ihre eigenen untergeordnete Elemente verfügen. In allen diesen Fällen wird das übergeordnete Fenster zugehöriges untergeordnetes Fenster verwaltet, und Sie einige Befehle aus, um diese leitet.

In einer MDI-Rahmenfenster verwaltet das Rahmenfenster der MDICLIENT-Fenster, in Verbindung mit Schiebeleisten-Steuerelemente neu positionieren. Die MDICLIENT-Fenster verwaltet wiederum alle MDI-untergeordneten Rahmenfenster. Die folgende Abbildung zeigt die Beziehung zwischen einer MDI-Rahmenfenster, das MDICLIENT-Fenster und seine untergeordneten Dokumentrahmenfenster.

![Untergeordnete Fenster in ein MDI-Rahmenfenster](../mfc/media/vc37gb1.gif "vc37gb1") MDI-Frame-Windows und untergeordneten Elementen

Ein MDI-Rahmenfenster funktioniert auch in Verbindung mit der aktuellen untergeordneten MDI-Fensters, falls vorhanden. MDI-Rahmenfensters mitverwenden delegiert Command-Meldungen auf untergeordneten MDI-Fensters auf, bevor er versucht, diese selbst zu behandeln.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Erstellen eines Dokuments Rahmenfenster](../mfc/creating-document-frame-windows.md)

- [Rahmenfensterstile](../mfc/frame-window-styles-cpp.md)

## <a name="see-also"></a>Siehe auch

[Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)

