---
title: Registrieren von Fensterklassen
ms.date: 11/04/2016
f1_keywords:
- WndProc
helpviewer_keywords:
- window classes [MFC], registering
- registry [MFC], registering classes
- AfxRegisterWndClass method [MFC]
- MFC, windows
- WinMain method [MFC], and registering window classes
- WndProc method [MFC]
- classes [MFC], registering window classes
- WinMain method [MFC]
- registering window classes [MFC]
ms.assetid: 30994bc4-a362-43da-bcc5-1bf67a3fc929
ms.openlocfilehash: 7c459b909a60fff2b7aeded9ea8d79a39ced24e4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57258423"
---
# <a name="registering-window-classes"></a>Registrieren von Fensterklassen

Fenster "Klassen" bei der traditionellen Programmierung für Windows definieren die Merkmale von einer "Class" (keine C++-Klasse) aus dem eine beliebige Anzahl von Windows erstellt werden kann. Diese Art von Klasse ist eine Vorlage oder das Modell zum Erstellen von Windows.

## <a name="window-class-registration-in-traditional-programs-for-windows"></a>Fensterklassenregistrierung in herkömmlichen Programmen für Windows

In einem herkömmlichen Programm für Windows, ohne MFC, verarbeiten Sie alle Nachrichten an ein Fenster in der Fensterprozedur"" oder "`WndProc`." Ein `WndProc` ein Fenster über einen Prozess "fensterklassenregistrierung" zugeordnet ist. Das Hauptfenster ist registriert, der `WinMain` -Funktion, aber andere Klassen von Windows registriert werden können eine beliebige Stelle in der Anwendung. Die Registrierung auf eine Struktur, die einen Zeiger auf enthält hängt der `WndProc` Funktion zusammen mit den Spezifikationen für den Cursor Hintergrundpinsel, und so weiter. Die Struktur wird als Parameter zusammen mit den Namen der in einem vorherigen Aufruf von der Klasse übergeben die `RegisterClass` Funktion. Daher kann eine Registrierungsklasse von mehreren Windows freigegeben werden.

## <a name="window-class-registration-in-mfc-programs"></a>Fensterklassenregistrierung in MFC-Programmen

Im Gegensatz dazu erfolgt Registrierungsaktivität für die meisten Fensterklassen automatisch in einem MFC-Framework-Programm. Wenn Sie MFC verwenden, leiten Sie eine C++-Fenster-Klasse in der Regel von einer vorhandenen Bibliotheksklasse, die mit der normalen C++-Syntax für klassenvererbung. Das Framework immer noch traditionelle verwendet "Registrierung Classes" und enthält mehrere standard-Handler, der für die Sie bei Bedarf registriert. Sie können weitere Klassen registrieren, durch den Aufruf der [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) globale Funktion und deren Übergabe der registrierten Klasse auf die `Create` Memberfunktion `CWnd`. Wie im folgenden beschrieben, die herkömmlichen "Registrierung Class" in Windows ist nicht zu verwechseln mit einer C++-Klasse.

Weitere Informationen finden Sie unter [technischen Hinweis 1](../mfc/tn001-window-class-registration.md).

## <a name="see-also"></a>Siehe auch

[Erstellen von Fenstern](../mfc/creating-windows.md)
