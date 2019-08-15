---
title: Beziehung zum C-Sprachen-API
ms.date: 11/04/2016
f1_keywords:
- vc.classes.mfc
helpviewer_keywords:
- books [MFC], about MFC and Windows SDK
- books [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- Windows API [MFC], and MFC
ms.assetid: 334e8efc-f3cc-4018-bc2e-02908b2a39fe
ms.openlocfilehash: 8601dd034dbd73ac035084ad57c51f62e333fd32
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511857"
---
# <a name="relationship-to-the-c-language-api"></a>Beziehung zum C-Sprachen-API

Das einzige Merkmal, das die MFC-Bibliothek (Microsoft Foundation Class) außer anderen Klassenbibliotheken für Windows festlegt, ist die sehr enge Zuordnung zur Windows-API, die in der Programmiersprache C geschrieben ist. Außerdem können Sie Aufrufe der Klassenbibliothek im allgemeinen kostenlos mit direkten Aufrufen der Windows-API mischen. Dieser direkte Zugriff bedeutet jedoch nicht, dass die Klassen ein kompletter Ersatz für diese API sind. Entwickler müssen einige Windows-Funktionen, wie z. b. [SetCursor](/windows/win32/api/winuser/nf-winuser-setcursor) und [GetSystemMetrics](/windows/win32/api/winuser/nf-winuser-getsystemmetrics), gelegentlich auch direkt aufrufen. Eine Windows-Funktion wird nur dann von einer Klassenmember-Funktion umschließt, wenn ein eindeutiger Vorteil vorliegt.

Da Sie manchmal systemeigene Windows-Funktionsaufrufe durchführen müssen, sollten Sie Zugriff auf die C-Sprache der Windows-API haben. Diese Dokumentation ist in Microsoft Visual C++enthalten.

> [!NOTE]
>  Eine Übersicht über die Funktionsweise des MFC-Bibliotheks-Frameworks finden [Sie unter Verwenden der Klassen zum Schreiben von Anwendungen für Windows](../mfc/using-the-classes-to-write-applications-for-windows.md).

## <a name="see-also"></a>Siehe auch

[Allgemeine Prinzipien für den Klassenentwurf](../mfc/general-class-design-philosophy.md)
