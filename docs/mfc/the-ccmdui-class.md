---
title: Die CCmdUI-Klasse
ms.date: 11/04/2016
f1_keywords:
- CCmdUI
helpviewer_keywords:
- updating user interface objects [MFC]
- user interface objects [MFC], updating
- CCmdUI class [MFC], menu updating
- update handlers [MFC]
- toolbars [MFC], updating
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
ms.openlocfilehash: 47ef359f71d9dd30f2ba1ff1c4cf504bccd33ffd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667947"
---
# <a name="the-ccmdui-class"></a>Die CCmdUI-Klasse

Wenn sie einen Update-Befehl an seinen Handler weitergeleitet wird, das Framework übergibt dem Handler für ein Zeiger auf eine `CCmdUI` Objekt (oder auf ein Objekt eine `CCmdUI`-abgeleitete Klasse). Dieses Objekt darstellt, die im Menü oder eine Symbolleisten-Schaltfläche oder ein anderes Benutzeroberflächen-Objekt, das den Befehl generiert. Vom updatehandler Ruft Funktionen des die `CCmdUI` -Struktur durch den Zeiger auf das Objekt für die Benutzeroberfläche zu aktualisieren. Hier ist z. B. ein updatehandler für das Menüelement alle löschen:

[!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]

Dieser Ereignishandler ruft die `Enable` Memberfunktion ein Objekt mit Zugriff auf das Menüelement. `Enable` Wandelt das Element für die Verwendung verfügbar.

## <a name="see-also"></a>Siehe auch

[Vorgehensweise: Aktualisieren von Benutzeroberflächenobjekten](../mfc/how-to-update-user-interface-objects.md)

