---
title: Beziehung zwischen einem C++-Fensterobjekt und einem HWND | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: HWND
dev_langs: C++
helpviewer_keywords:
- Windows window [MFC]
- window objects [MFC], HWND and
- HWND [MFC]
- CWnd class [MFC], HWND
- HWND, window objects [MFC]
ms.assetid: f2e76340-6691-4ee6-9424-0345634a9469
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b441077de3a81de569627b6d7acf7cee8ca17b33
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="relationship-between-a-c-window-object-and-an-hwnd"></a>Beziehung zwischen einem C++-Fensterobjekt und einem HWND
Das Fenster *Objekt* ist ein Objekt der C++-Komponente `CWnd` -Klasse (oder einer abgeleiteten Klasse), die das Programm direkt erstellt. Es kommt und wird als Antwort auf das Programm Konstruktor und Destruktor aufruft. Die Windows *Fenster*, andererseits, ist ein nicht transparentes Handle zu einer internen Windows-Datenstruktur, die einem Fenster entspricht und Systemressourcen vorhanden. Ein Windows-Fenster wird durch ein "Fensterhandle" identifiziert (`HWND`) und wird erstellt, nachdem die `CWnd` objekterstellung durch einen Aufruf der **erstellen** Memberfunktion der Klasse `CWnd`. Das Fenster kann entweder durch einen Aufruf der Anwendung oder durch eine Benutzeraktion zerstört werden. Das Fensterhandle wird gespeichert, in des Fensterobjekts `m_hWnd` Membervariablen gespeichert. Die folgende Abbildung zeigt die Beziehung zwischen C++-Fensterobjekt und das Windows-Fenster. Erstellen von Fenstern wird erläutert, [erstellen Windows](../mfc/creating-windows.md). Zerstören von Fenstern finden [Zerstören von Fensterobjekten](../mfc/destroying-window-objects.md).  
  
 ![CWnd-Fensterobjekt und resultierendes Fenster](../mfc/media/vc37fj1.gif "vc37fj1")  
window-Objekt und Windows-Fenster  
  
## <a name="see-also"></a>Siehe auch  
 [Fensterobjekte](../mfc/window-objects.md)

