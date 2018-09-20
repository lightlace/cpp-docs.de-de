---
title: Beziehung zwischen einem C++-Fensterobjekt und einem HWND | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- HWND
dev_langs:
- C++
helpviewer_keywords:
- Windows window [MFC]
- window objects [MFC], HWND and
- HWND [MFC]
- CWnd class [MFC], HWND
- HWND, window objects [MFC]
ms.assetid: f2e76340-6691-4ee6-9424-0345634a9469
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 844f62b110f54ba3e2c8909a78d58c9f2c01dcac
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392813"
---
# <a name="relationship-between-a-c-window-object-and-an-hwnd"></a>Beziehung zwischen einem C++-Fensterobjekt und einem HWND

Das Fenster *Objekt* ist ein Objekt der C++- `CWnd` -Klasse (oder in einer abgeleiteten Klasse), die Ihre Anwendung direkt erstellt. Er stammt und wird als Reaktion auf Ihres Programms Konstruktor und Destruktor aufrufen. Die Windows *Fenster*, auf der anderen Seite ist ein nicht transparentes Handle auf eine interne Windows-Datenstruktur, die in einem Fenster entspricht und beansprucht Systemressourcen vorhanden. Ein Windows-Fenster wird durch ein "Fensterhandle" identifiziert (`HWND`) und erstellt wird, nachdem die `CWnd` objekterstellung durch einen Aufruf der `Create` Memberfunktion der Klasse `CWnd`. Das Fenster kann entweder durch einen Aufruf der Anwendung oder durch die Aktion eines Benutzers zerstört werden. Das Handle des Fensters befindet sich in des Fensterobjekts *M_hWnd* Membervariablen gespeichert. Die folgende Abbildung zeigt die Beziehung zwischen dem C++-Fensterobjekt und das Windows-Fenster. Erstellen von Windows erläutert [erstellen Windows](../mfc/creating-windows.md). Zerstören von Fenstern ausführlicher [Zerstören von Fensterobjekten](../mfc/destroying-window-objects.md).

![CWnd-Fensterobjekt und resultierendes Fenster](../mfc/media/vc37fj1.gif "vc37fj1") -Fensterobjekt und Windows-Fenster

## <a name="see-also"></a>Siehe auch

[Fensterobjekte](../mfc/window-objects.md)

