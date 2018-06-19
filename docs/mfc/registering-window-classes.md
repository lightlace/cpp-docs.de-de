---
title: Registrieren von Fensterklassen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- WndProc
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 00e397f8880f6f42f1930e668b64d3ba62eb2c64
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379741"
---
# <a name="registering-window-classes"></a>Registrieren von Fensterklassen
Fenster "Classes" in der herkömmlichen Programmierung für Windows definieren die Merkmale einer "Klasse" (keiner C++-Klasse) aus dem eine beliebige Anzahl von Windows erstellt werden kann. Diese Art der Klasse ist eine Vorlage oder ein Modell zum Erstellen von Windows.  
  
## <a name="window-class-registration-in-traditional-programs-for-windows"></a>Fensterklassenregistrierung in herkömmlichen Programmen für Windows  
 In einem herkömmlichen-Programm für Windows, ohne MFC, verarbeiten Sie alle Nachrichten in einem Fenster in der Fensterprozedur"" oder "**WndProc**." Ein **WndProc** eines Fensters durch einen Prozess "fensterklassenregistrierung" zugeordnet ist. Das Hauptfenster wird registriert, der `WinMain` -Funktion, aber andere Klassen von Windows registriert werden können eine beliebige Stelle in der Anwendung. Registrierung hängt eine Struktur, die einen Zeiger auf die **WndProc** Funktion zusammen mit den Spezifikationen für den Cursor, Hintergrundpinsel, und so weiter. Die Struktur wird als Parameter zusammen mit dem Zeichenfolgennamen "der Klasse in einem vorherigen Aufruf zum Übergeben der **RegisterClass** Funktion. Daher kann eine Registrierungsklasse von mehreren Windows freigegeben werden.  
  
## <a name="window-class-registration-in-mfc-programs"></a>Fensterklassenregistrierung in MFC-Programmen  
 Im Gegensatz dazu erfolgt Registrierungsaktivität für die meisten Fensterklassen automatisch in einem MFC-Framework-Programm. Bei Verwendung von MFC leiten Sie eine C++-Fenster-Klasse in der Regel mit normaler C++-Syntax für die klassenvererbung einer vorhandenen Bibliothek-Klasse. Das Framework verwendet weiterhin herkömmlichen "Klassen", und es enthält mehrere standard Beziehungen, die für Sie bei Bedarf registriert. Sie können weitere Klassen registrieren, durch Aufrufen der [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) globale Funktion und deren Übergabe der registrierten Klasse, um die **erstellen** Memberfunktion von `CWnd`. Hier die herkömmlichen beschriebenen "Registrierungsklasse" in Windows ist nicht zu verwechseln mit einer C++-Klasse.  
  
 Weitere Informationen finden Sie unter [technischen Hinweis 1](../mfc/tn001-window-class-registration.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Fenstern](../mfc/creating-windows.md)

