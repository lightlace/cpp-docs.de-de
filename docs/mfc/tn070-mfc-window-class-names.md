---
title: 'TN070: MFC-Fensterklassennamen'
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.classes
helpviewer_keywords:
- window class names [MFC]
- TN070 [MFC]
ms.assetid: 90617912-dd58-4a7c-9082-ced71736d7cd
ms.openlocfilehash: d59dc052cc253c8d036de0559018065e4ba7457d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533613"
---
# <a name="tn070-mfc-window-class-names"></a>TN070: MFC-Fensterklassennamen

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

MFC-Windows verwenden Sie einen dynamisch erstellte Klasse-Namen, der die Funktionen des Fensters darstellt. MFC generiert Klassennamen dynamisch für Popup-Fenster, die von der Anwendung erzeugten, Ansichten und Rahmenfenster. Haben den Namen Windows bereitgestellte, für die Klasse des betreffenden Fenster, Dialogfelder und Steuerelemente, die von einer MFC-Anwendung erzeugt.

Sie können den Namen der dynamisch bereitgestellte Klasse ersetzen, indem Sie eigene Fensterklasse registrieren und verwenden es in einer Außerkraftsetzung der [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow). Die Klassennamen MFC bereitgestellten lassen sich einer der beiden folgenden Formen:

```
Afx:%x:%x
Afx:%x:%x:%x:%x:%x
```

Die hexadezimale Ziffern, die ersetzt die `%x` Zeichen werden von den Daten ausgefüllt der [WNDCLASS](https://msdn.microsoft.com/library/windows/desktop/ms633576) Struktur. MFC verwendet dieses Verfahren, damit mehrere C++-Klassen, die erfordern einen identischen **WNDCLASS** Strukturen können die gleichen registrierten Fensterklasse freigeben. MFC-Anwendungen im Gegensatz zu den meisten einfachen Win32-Anwendungen haben nur eine **WNDPROC**, sodass Sie ganz einfach freigeben können **WNDCLASS** Strukturen, um Zeit und Arbeitsspeicher zu sparen. Die ersetzbaren Werte für die `%x` Zeichen, die oben gezeigte sind wie folgt:

- **WNDCLASS.hInstance**

- **WNDCLASS.style**

- **WNDCLASS.hCursor**

- **WNDCLASS.hbrBackground**

- **WNDCLASS.hIcon**

Die erste Form (`Afx:%x:%x`) wird verwendet, wenn **hCursor**, **HbrBackground**, und **hIcon** sind alle **NULL**.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)<br/>
[TN020: ID-Benennungs- und Nummerierungskonventionen](../mfc/tn020-id-naming-and-numbering-conventions.md)

