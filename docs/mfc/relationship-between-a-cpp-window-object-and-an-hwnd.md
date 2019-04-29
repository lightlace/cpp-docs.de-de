---
title: Beziehung zwischen einem C++-Fensterobjekt und einem HWND
ms.date: 11/19/2018
f1_keywords:
- HWND
helpviewer_keywords:
- Windows window [MFC]
- window objects [MFC], HWND and
- HWND [MFC]
- CWnd class [MFC], HWND
- HWND, window objects [MFC]
ms.assetid: f2e76340-6691-4ee6-9424-0345634a9469
ms.openlocfilehash: 8cf8856be7166768c507932184e257cf69b0eb35
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62309322"
---
# <a name="relationship-between-a-c-window-object-and-an-hwnd"></a>Beziehung zwischen einem C++-Fensterobjekt und einem HWND

Das Fenster *Objekt* ist ein Objekt der C++- `CWnd` -Klasse (oder in einer abgeleiteten Klasse), die Ihre Anwendung direkt erstellt. Er stammt und wird als Reaktion auf Ihres Programms Konstruktor und Destruktor aufrufen. Die Windows *Fenster*, auf der anderen Seite ist ein nicht transparentes Handle auf eine interne Windows-Datenstruktur, die in einem Fenster entspricht und beansprucht Systemressourcen vorhanden. Ein Windows-Fenster wird durch ein "Fensterhandle" identifiziert (`HWND`) und erstellt wird, nachdem die `CWnd` objekterstellung durch einen Aufruf der `Create` Memberfunktion der Klasse `CWnd`. Das Fenster kann entweder durch einen Aufruf der Anwendung oder durch die Aktion eines Benutzers zerstört werden. Das Handle des Fensters befindet sich in des Fensterobjekts *M_hWnd* Membervariablen gespeichert. Die folgende Abbildung zeigt die Beziehung zwischen dem C++-Fensterobjekt und das Windows-Fenster. Erstellen von Windows erläutert [erstellen Windows](../mfc/creating-windows.md). Zerstören von Fenstern ausführlicher [Zerstören von Fensterobjekten](../mfc/destroying-window-objects.md).

![CWnd-Fensterobjekt und resultierendes Fenster](../mfc/media/vc37fj1.gif "CWnd-Fensterobjekt und resultierendes Fenster") <br/>
window-Objekt und Windows-Fenster

## <a name="see-also"></a>Siehe auch

[Fensterobjekte](../mfc/window-objects.md)
