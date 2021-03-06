---
title: Allgemeine Ablauffolge bei der Fenstererstellung
ms.date: 11/04/2016
helpviewer_keywords:
- sequence [MFC], window creation
- frame windows [MFC], creating
- windows [MFC], creating
- sequence [MFC]
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
ms.openlocfilehash: 949cf72910654b502ca4b57be72bedc2db63c315
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219563"
---
# <a name="general-window-creation-sequence"></a>Allgemeine Ablauffolge bei der Fenstererstellung

Wenn Sie ein Fenster in Ihrem eigenen, z. B. ein untergeordnetes Fenster erstellen, verwendet das Framework viel den gleichen Prozess als beschrieben. [Dokument-/Ansicht-Erstellung](../mfc/document-view-creation.md).

Aller Fensterklassen, die von MFC einsetzen bereitgestellten [zweistufige Konstruktion](../mfc/one-stage-and-two-stage-construction-of-objects.md). D. h. während eines Aufrufs der C++- **neue** -Operator, der Konstruktor weist und initialisiert ein C++-Objekt aber einen entsprechenden Windows-Fenster nicht erstellt. Erfolgt anschließend durch Aufrufen der [erstellen](../mfc/reference/cwnd-class.md#create) -Memberfunktion des Window-Objekts.

Die `Create` Memberfunktion wird die Windows-Fenster und speichert die `HWND` in die C++ öffentlichen Datenmember des Objekts [M_hWnd](../mfc/reference/cwnd-class.md#m_hwnd). `Create` Führen Sie erhalten Flexibilität über die Erstellungsparameter. Vor dem Aufruf `Create`, Sie möchten mit der globalen-Funktion eine Fensterklasse registrieren [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) um die Stile-Symbol und die Klasse für den Frame festzulegen.

Für das Rahmenfenster, können Sie die [LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) Memberfunktion anstelle der `Create`. `LoadFrame` Stellt das Windows-Fenster, das mit weniger Parametern. Es ruft viele Standardwerte aus Ressourcen, einschließlich des Frames Beschriftung, Symbol, Zugriffstastentabelle und im Menü ab.

> [!NOTE]
>  Ihr Symbol Zugriffstastentabelle und Menüressourcen benötigen eine allgemeine Ressourcen-ID, wie z. B. **IDR_MAINFRAME**, für die sie von LoadFrame geladen werden.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Fensterobjekte](../mfc/window-objects.md)

- [Registrieren von Fensterklassen""](../mfc/registering-window-classes.md)

- [Zerstören von Fensterobjekten](../mfc/destroying-window-objects.md)

- [Erstellen eines Dokuments Rahmenfenster](../mfc/creating-document-frame-windows.md)

## <a name="see-also"></a>Siehe auch

[Erstellen von Fenstern](../mfc/creating-windows.md)
