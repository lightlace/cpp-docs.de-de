---
title: 'TN070: MFC-Fenster Klassennamen'
ms.date: 11/04/2016
helpviewer_keywords:
- window class names [MFC]
- TN070 [MFC]
ms.assetid: 90617912-dd58-4a7c-9082-ced71736d7cd
ms.openlocfilehash: 1d9b5de07bcc2545df6294557d1ac9f9d29e856c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513358"
---
# <a name="tn070-mfc-window-class-names"></a>TN070: MFC-Fenster Klassennamen

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

MFC-Fenster verwenden einen dynamisch erstellten Klassennamen, der die Funktionen des Fensters widerspiegelt. MFC generiert Klassennamen dynamisch für Frame Fenster, Ansichten und Popup Fenster, die von der Anwendung erstellt werden. Dialog Felder und Steuerelemente, die von einer MFC-Anwendung erstellt wurden, verfügen über den von Windows bereitgestellten Namen für die betreffende Fenster Klasse.

Sie können den dynamisch bereitgestellten Klassennamen ersetzen, indem Sie eine eigene Fenster Klasse registrieren und Sie in einer Überschreibung von [prekreatewindow](../mfc/reference/cwnd-class.md#precreatewindow)verwenden. Die von MFC bereitgestellten Klassennamen passen zu einem der beiden folgenden Formate:

```
Afx:%x:%x
Afx:%x:%x:%x:%x:%x
```

Die hexadezimal Ziffern `%x` , die die Zeichen ersetzen, werden aus Daten aus der [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) -Struktur ausgefüllt. MFC verwendet dieses Verfahren, sodass mehrere C++ Klassen, die identische **WNDCLASS** -Strukturen erfordern, dieselbe registrierte Fenster Klasse gemeinsam verwenden können. Im Gegensatz zu den meisten einfachen Win32-Anwendungen haben MFC-Anwendungen nur einen **WndProc**, sodass Sie einfach **WNDCLASS** -Strukturen freigeben können, um Zeit und Arbeitsspeicher zu sparen. Die ersetzbaren Werte für `%x` die oben gezeigten Zeichen lauten wie folgt:

- **WNDCLASS. HINSTANCE**

- **WNDCLASS. Style**

- **WNDCLASS. hcursor**

- **WNDCLASS. hbrbackground**

- **WNDCLASS.hIcon**

Das erste Formular (`Afx:%x:%x`) wird verwendet, wenn **hcursor**, **hbrbackground**und **HICON** alle **null**sind.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)<br/>
[TN020: ID-Benennungs- und Nummerierungskonventionen](../mfc/tn020-id-naming-and-numbering-conventions.md)
