---
title: Beziehung zwischen einem C++-Fensterobjekt und einem HWND | Microsoft Docs
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
ms.openlocfilehash: b51daa375c3c920443316b6e10b6415ee018fdb4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="relationship-between-a-c-window-object-and-an-hwnd"></a>Beziehung zwischen einem C++-Fensterobjekt und einem HWND
Das Fenster *Objekt* ist ein Objekt der C++-Komponente `CWnd` -Klasse (oder einer abgeleiteten Klasse), die das Programm direkt erstellt. Es kommt und wird als Antwort auf das Programm Konstruktor und Destruktor aufruft. Die Windows *Fenster*, andererseits, ist ein nicht transparentes Handle zu einer internen Windows-Datenstruktur, die einem Fenster entspricht und Systemressourcen vorhanden. Ein Windows-Fenster wird durch ein "Fensterhandle" identifiziert (`HWND`) und wird erstellt, nachdem die `CWnd` objekterstellung durch einen Aufruf der **erstellen** Memberfunktion der Klasse `CWnd`. Das Fenster kann entweder durch einen Aufruf der Anwendung oder durch eine Benutzeraktion zerstört werden. Das Fensterhandle wird gespeichert, in des Fensterobjekts `m_hWnd` Membervariablen gespeichert. Die folgende Abbildung zeigt die Beziehung zwischen C++-Fensterobjekt und das Windows-Fenster. Erstellen von Fenstern wird erläutert, [erstellen Windows](../mfc/creating-windows.md). Zerstören von Fenstern finden [Zerstören von Fensterobjekten](../mfc/destroying-window-objects.md).  
  
 ![CWnd-Fensterobjekt und resultierendes Fenster](../mfc/media/vc37fj1.gif "vc37fj1")  
window-Objekt und Windows-Fenster  
  
## <a name="see-also"></a>Siehe auch  
 [Fensterobjekte](../mfc/window-objects.md)

