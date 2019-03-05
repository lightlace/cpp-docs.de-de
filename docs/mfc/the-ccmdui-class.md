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
ms.openlocfilehash: 8e0af0703924d6fae626d3753b8523efe0c56652
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57326618"
---
# <a name="the-ccmdui-class"></a>Die CCmdUI-Klasse

Wenn sie einen Update-Befehl an seinen Handler weitergeleitet wird, das Framework übergibt dem Handler für ein Zeiger auf eine `CCmdUI` Objekt (oder auf ein Objekt eine `CCmdUI`-abgeleitete Klasse). Dieses Objekt darstellt, die im Menü oder eine Symbolleisten-Schaltfläche oder ein anderes Benutzeroberflächen-Objekt, das den Befehl generiert. Vom updatehandler Ruft Funktionen des die `CCmdUI` -Struktur durch den Zeiger auf das Objekt für die Benutzeroberfläche zu aktualisieren. Hier ist z. B. ein updatehandler für das Menüelement alle löschen:

[!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]

Dieser Ereignishandler ruft die `Enable` Memberfunktion ein Objekt mit Zugriff auf das Menüelement. `Enable` Wandelt das Element für die Verwendung verfügbar.

## <a name="see-also"></a>Siehe auch

[Vorgehensweise: Aktualisieren von Benutzeroberflächenobjekten](../mfc/how-to-update-user-interface-objects.md)
